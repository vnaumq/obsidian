[[Distributed System Concepts]]

## **CAP Theorem Definition**

In computer science, the CAP theorem, sometimes called CAP theorem model or Brewer’s theorem after its originator, Eric Brewer, states that any distributed system or data store can simultaneously provide only two of three guarantees: consistency, availability, and partition tolerance (CAP).

During times of normal operations, a data store covers all three. However, according to the CAP theorem, a [distributed database](https://www.scylladb.com/glossary/distributed-database/) system can provide **either** consistency **or** availability when it experiences a network failure. In other words, in case of a network failure, it’s a tradeoff between consistency or availability, and that choice must be made in advance.

The theorem states that a distributed database requires partition tolerance. The distributed data store, by nature, operates with network partitions, so because network failures are inevitable, partition tolerance is necessary to reliable service.This means users need to choose between C (consistency) and A (availability) in case a network failure occurs and both availability and consistency cannot be guaranteed. The cost of high availability is lower consistency. The price of high consistency is lower availability.

![[cap-theorem-diagram-e1647300692559.webp]]

## What is CAP Theorem?

Understanding the CAP theorem is simpler when you consider it piece by piece:

**What is CAP theorem in distributed systems?** A distributed network system stores data across multiple nodes—virtual or physical machines—simultaneously. It’s essential to understand the CAP theorem when designing a cloud application because all cloud apps are distributed systems.

**What is CAP theorem consistency****?** Consistency of CAP theorem means that regardless of the node they connect to, all clients see the same data at once. For the write to one node to succeed, it must also instantly be replicated or forwarded to all the other nodes in the system.

**CAP theorem eventual consistency.** Some NoSQL databases (for example, ScyllaDB) use  a model of tunable eventual consistency to deliver multi datacenter high availability and fast and efficient write and read operations. In this case, all nodes are equal; this means any node can serve any request, there is no single point of coordination, and all nodes in the system continue to cooperatively provide service, even when nodes become unavailable. [Eventual consistency](https://www.scylladb.com/glossary/eventual-consistency/) supports modern workloads that are less dependent on strong consistency but rely heavily on availability.

**What is availability in CAP theorem?** CAP theorem availability means that even if one or more nodes are down, any client making a data request receives a response. In other words, when any request is made, without exception, all working nodes in a distributed system return a valid response.

**Partition tolerance in** **CAP theorem explained****.** In a distributed system, a partition is a break in communications—a temporarily delayed or lost connection between nodes. Partition tolerance means that in spite of any number of breakdowns in communication between nodes in the system, the cluster will continue to work.

**What is CAP theorem in NoSQL?** [NoSQL databases](https://www.scylladb.com/learn/nosql/) and CAP theorem are closely linked. NoSQL databases are categorized based on which CAP characteristics they support: CP, AP, or CA.

## CAP Theorem vs ACID

Although the “C” in both ACID and CAP theorem refer to consistency, consistency in CAP is different than in ACID. In CAP, consistency means having information that is the most up-to-date. Consistency in ACID refers to the hardness of the database that protects it from corruption despite the addition of new transactions and references different database events.

Database systems such as RDBMS that are designed in part based on traditional ACID guarantees choose consistency over availability. In contrast, systems common in the NoSQL movement designed around the BASE philosophy select availability over consistency.

