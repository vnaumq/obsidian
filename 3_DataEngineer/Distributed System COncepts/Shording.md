[[Distributed System Concepts]]

## What is database sharding?

Database sharding is the process of storing a large database across multiple machines. A single machine, or database server, can store and process only a limited amount of data. Database sharding overcomes this limitation by splitting data into smaller chunks, called shards, and storing them across several database servers. All database servers usually have the same underlying technologies, and they work together to store and process large volumes of data.

## Why is database sharding important? 

As an application grows, the number of application users and the amount of data it stores increase over time. The database becomes a bottleneck if the data volume becomes too large and too many users attempt to use the application to read or save information simultaneously. The application slows down and affects customer experience. Database sharding is one of the methods to solve this problem because it enables parallel processing of smaller datasets across shards.

## What are the benefits of database sharding? 

Organizations use database sharding to gain the following benefits:

### **Improve response time**

Data retrieval takes longer on a single large database. The [database management system](https://aws.amazon.com/products/databases/) needs to search through many rows to retrieve the correct data. By contrast, data shards have fewer rows than the entire database. Therefore, it takes less time to retrieve specific information, or run a query, from a sharded database. 

### **Avoid total service outage**

If the computer hosting the database fails, the application that depends on the database fails too. Database sharding prevents this by distributing parts of the database into different computers. Failure of one of the computers does not shut down the application because it can operate with other functional shards. Sharding is also often done in combination with data replication across shards. So, if one shard becomes unavailable, the data can be accessed and restored from an alternate shard.

### **Scale efficiently**

A growing database consumes more computing resources and eventually reaches storage capacity. Organizations can use database sharding to add more computing resources to support database scaling. They can add new shards at runtime without shutting down the application for maintenance.

### **Shards**

The partitioned data chunks are called logical shards. The machine that stores the logical shard is called a physical shard or database node. A physical shard can contain multiple logical shards. 

### **Shard key**

Software developers use a shard key to determine how to partition the dataset. A column in the dataset determines which rows of data group together to form a shard. Database designers choose a shard key from an existing column or create a new one.

### **Shared-nothing architecture**

Database sharding operates on a shared-nothing architecture. Each physical shard operates independently and is unaware of other shards. Only the physical shards that contain the data that you request will process the data in parallel for you. 

A software layer coordinates data storage and access from these multiple shards. For example, some types of database technology have automatic sharding features built in. Software developers can also write sharding code in their application to store or retrieve information from the correct shard or shards.