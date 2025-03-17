[[NewSQL]]

## What is NewSQL?

NewSQL is a class of relational database management systems ([[RDBMS]]) designed to provide the scalability of NoSQL systems for online transaction processing ([[OLTP]]) read-write workloads while maintaining the [[ACID]] guarantees ([[Atomicity]], [[Consistency]],[[ Isolation]], [[Durability]]) of traditional database systems. It delivers a modern solution where businesses can handle large volumes of data in real-time, without having to sacrifice consistency or reliability.

## History

The term NewSQL was coined by 451 Research analyst Matt Aslett in 2011, and has been adopted by a number of vendors who do not fit into the traditional [RDBMS](https://www.dremio.com/wiki/rdbms/) mold, yet also diverge from the NoSQL movement. NewSQL systems are designed to operate in distributed clusters like NoSQL databases, but they present a relational model and support SQL query semantics.

## Functionality and Features

NewSQL databases offer a range of features and functions aimed at preserving SQL's robustness while enhancing scalability and performance. These include:

- Full support for SQL: The ability to process complex SQL queries, a feature that's not typically available in NoSQL databases.
- Scalability: The ability to [scale horizontally](https://www.dremio.com/wiki/horizontal-scaling/) across multiple nodes for high-volume traffic while maintaining high transaction rates.
- Fault Tolerance: The inclusion of mechanisms to prevent data loss in case of system failure.
- Distributed Transactions: Support for ACID transactions across distributed databases.
- Built-In Machine Learning: Some NewSQL databases incorporate machine learning functionality directly into the database.

## Architecture

The architecture of NewSQL databases is typically distributed and scales horizontally. The system architecture is composed of multiple layers including a SQL layer and a distributed transactional storage layer. The SQL layer processes queries and transactions, while the storage layer manages distributed data access and controls concurrency and recovery.

## Benefits and Use Cases

NewSQL fills the gap between traditional RDBMS and NoSQL databases, making it suitable for a variety of use cases. It is particularly well-suited for applications that require high transactional throughput along with strict consistency, such as financial systems and online retail applications. It also benefits big data analytics by providing a scalable database layer that supports complex SQL queries.

## Challenges and Limitations

While NewSQL databases offer many advantages, they are not without limitations. For instance, NewSQL services can be complex to administer due to their distributed nature. Also, as a newer technology, they may not yet offer the complete suite of tools and functionalities provided by mature RDBMS platforms.