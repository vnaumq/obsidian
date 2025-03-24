[[NoSQL]]

These days, [time-series data](https://www.timescale.com/blog/time-series-data/) applications (e.g., data center / server / microservice / container monitoring, sensor / IoT analytics, financial data analysis, etc.) are proliferating.

As a result, time-series databases are in fashion ([here are 33 of them](https://misfra.me/2016/04/09/tsdb-list/)). Most of these renounce the trappings of a traditional relational database and adopt what is generally known as a NoSQL model. Usage patterns are similar: [a recent survey](https://www.percona.com/blog/2017/02/10/percona-blog-poll-database-engine-using-store-time-series-data/) showed that developers preferred NoSQL to relational databases for time-series data by over 2:1.

Typically, the reason for adopting NoSQL time-series databases comes down to scale. While relational databases have many useful features that most NoSQL databases do not (robust secondary index support; complex predicates; a rich query language; JOINs, etc), they are difficult to scale.

And because time-series data piles up very quickly, many developers believe relational databases are ill-suited for it.

We take a different, somewhat heretical stance: relational databases can be quite powerful for time-series data. One just needs to solve the scaling problem. That is what we do in [TimescaleDB](https://github.com/timescale/timescaledb).

When we [announced TimescaleDB two weeks ago](https://www.timescale.com/blog/when-boring-is-awesome-building-a-scalable-time-series-database-on-postgresql-2900ea453ee2/), we received a lot of positive feedback from the community. But we also heard from skeptics, who found it hard to believe that one should (or could) build a scalable time-series database on a relational database (in our case, PostgreSQL).

There are two separate ways to think about scaling: ****scaling up**** so that a single machine can store more data, and ****scaling out**** so that data can be stored across multiple machines.

Why are both important? The most common approach to scaling out across a cluster of _N_ servers is to partition, or shard, a dataset into _N_ partitions. If each server is limited in its throughput or performance (i.e., unable to scale up), then the overall cluster throughput is greatly reduced.

This post discusses ****scaling up****. (A ****scaling-out**** post will be published on a later date.)

In particular, this post explains:

- Why relational databases do not normally scale up well
- How LSM trees (typically used in NoSQL databases) do not adequately solve the needs of many time-series applications
- How time-series data is unique, how one can leverage those differences to overcome the scaling problem, and some performance results

Our motivations are twofold: ****for anyone facing similar problems****, to share what we’ve learned; and ****for those considering using TimescaleDB for time-series data**** (including the skeptics!), to explain some of our design decisions.

Now let’s consider a few examples of time-series workloads:

- ****DevOps/server/container monitoring.**** The system typically collects metrics about different servers or containers: CPU usage, free/used memory, network tx/rx, disk IOPS, etc. Each set of metrics is associated with a timestamp, unique server name/ID, and a set of tags that describe an attribute of what is being collected.
- ****IoT sensor data.**** Each IoT device may report multiple sensor readings for each time period. As an example, for environmental and air quality monitoring this could include: temperature, humidity, barometric pressure, sound levels, measurements of nitrogen dioxide, carbon monoxide, particulate matter, etc. Each set of readings is associated with a timestamp and unique device ID, and may contain other metadata.
- ****Financial data.**** Financial tick data may include streams with a timestamp, the name of the security, and its current price and/or price change. Another type of financial data is payment transactions, which would include a unique account ID, timestamp, transaction amount, as well as any other metadata. (Note that this data is different than the OLTP example above: here we are recording every transaction, while the OLTP system was just reflecting the current state of the system.)
- ****Fleet/asset management.**** Data may include a vehicle/asset ID, timestamp, GPS coordinates at that timestamp, and any metadata.