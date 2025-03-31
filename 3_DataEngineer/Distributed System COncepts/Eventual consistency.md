[[Distributed System Concepts]]

## What is Eventual Consistency?

Consistency refers to a database query returning the same data each time the same request is made. Strong consistency means the latest data is returned, but, due to internal consistency methods, it may result with higher latency or delay. With eventual consistency, results are less consistent early on, but they are provided much faster with [low latency](https://www.scylladb.com/glossary/low-latency-database/). Early results of eventual consistency data queries may not have the most recent updates because it takes time for updates to reach replicas across a database cluster.

## What is Eventual Consistency In NoSQL?

A key benefit of an eventually consistent database is that it supports the high availability model of NoSQL. Eventually consistent databases prioritize availability over strong consistency. Eventual consistency in microservices can support an always-available API that must be responsive, even if the query results may occasionally be missing the latest commit.

## ACID vs. BASE: How is Eventual Consistency Similar to Strong Consistency?

Eventual consistency in general refers to a database’s ability to process transactions simultaneously while preserving the integrity of the data. In simple terms, inconsistency designates the guarantee that a READ should return the result of the latest successful WRITE. This seems simple, but such a guarantee is incredibly difficult to deliver in a globally distributed database topology, that involves multiple clusters each containing many nodes.

In general, relational databases that support ‘strong consistency’ provide ‘ACID guarantees’. ACID is an acronym designed to capture the essential elements of a strongly consistent database. The components of ACID are as follows:

- Atomicity – if transaction fails at any point, the entire operation rolls back
- Consistency – the database remains structurally sound with every transaction
- Isolation – each transaction is independent of any other transaction
- Durability – all transaction results are permanently preserved

ACID compliance is a complex and often contested topic. In fact, one popular system of analysis, the [Jepsen tests](https://jepsen.io/), are dedicated to verifying vendor consistency claims.

For this reason, ACID-compliant databases are generally slow, difficult to scale, and expensive to run and maintain. Some RDBMS systems, it should be noted, enable ACID guarantees to be relaxed. Still, all SQL databases are ACID compliant to varying degrees, they all share this downside. it is extraordinarily difficult and expensive to achieve resilient, [distributed SQL](https://www.scylladb.com/learn/distributed-sql-guide/) database deployments.

## ACID vs. BASE: How is Eventual Consistency Different from Strong Consistency?

A DBMS using the ACID model expects a unit of work to be atomic. It is all-or-nothing. While that unit of work is being done, the records or tables affected may be locked. [Distributed databases](https://www.scylladb.com/glossary/distributed-database/) with a BASE model give high availability. The records stay available, but once the transaction has completed across a majority of nodes, the transaction is deemed successful. Data replication across all nodes can take a little more time, but the data in all nodes will become consistent eventually. Once the transaction is deemed successful, queries for the data will consistently provide the updated data, even before data replication reaches the last few nodes.

Early results of eventual consistency data queries may not have the most recent updates. This is because it takes time for updates to reach replicas across a database cluster. In strong consistency, data is sent to every replica the moment a query is made. This causes delay because responses to any new requests must wait while the replicas are updated. When the data is consistent, the waiting requests are handled in the order they arrived and the cycle repeats.

In contrast to SQL’s ACID guarantees, NoSQL databases provide so-called BASE guarantees. A BASE enables availability and relaxes the stringent consistency. The acronym BASE designates:

- Basic Availability – Data is available most of the time, even during a partial system failure.
- Soft state – replicas are not consistent all the time.
- Eventual consistency – data will become consistent at some point in time, with no guarantee when.

As such, [NoSQL databases](https://www.scylladb.com/resources/what-is-nosql/) sacrifice a degree of consistency in order to increase availability. Rather than providing strong consistency, they provide eventual consistency. This means that a datastore that provides BASE guarantees can occasionally fail to return the result of the latest WRITE.

In a globally distributed eventual consistency NoSQL database deployment, some transactions might overlap. In a typical example, an eventual consistency NoSQL database might permit a hotel room to be reserved on the same night by two different customers, one in Hong Kong and the other in New York City. For many business applications, this is not a problem. The resilience, availability, and low-latency afforded by NoSQL are well worth the tradeoff. The hotel can provide perks to a disgruntled customer, but, by contrast, a regional outage could create significant churn.