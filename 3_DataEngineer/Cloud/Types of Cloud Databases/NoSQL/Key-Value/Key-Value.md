[[NoSQL]]

A [key-value database](https://aws.amazon.com/dynamodb/) is a type of non-relational database, also known as [NoSQL database](https://aws.amazon.com/nosql/), that uses a simple key-value method to store data. It stores data as a collection of key-value pairs in which a key serves as a unique identifier. Both keys and values can be anything, ranging from simple objects to complex compound objects. Key-value databases (or key-value stores) are highly partitionable and allow horizontal scaling at a level that other types of databases cannot achieve.

## What are the features of key-value databases
### Support for complex data types
Key-value stores provide support for defined data types like integers and text. However, many of them can also support more complex objects like arrays, nested dictionaries, images, videos, and semi-structured data. By giving the database more information about your data, there is room for more storage and query performance optimization.
### No need for table joins

Key-value databases don't need to perform any resource-intensive table joins. Their flexibility accommodates all the needed information in a single table. This is one of the reasons key-value stores perform so well.

### ACID support

Atomicity, Consistency, Isolation, and Durability ([ACID](https://docs.aws.amazon.com/athena/latest/ug/acid-transactions.html)) are database properties that ensure data accuracy and reliability in all circumstances. For instance, if you are making multiple changes to your data in a sequence, atomicity requires that all changes go through in order. If one change fails, everything fails.

Advanced key-value databases provide native, server-side support for ACID. This simplifies the developer experience of making coordinated, all-or-nothing changes to multiple items both within and across tables. With transaction support, developers can extend the scale, performance, and enterprise benefits to a broader set of mission-critical workloads.

## What are the use cases of key-value databases
### Session management

A session-oriented application, such as a web application, starts a session when a user logs in to an application and is active until the user logs out or the session times out. During this period, the application stores all user session attributes either in the main memory or in a database. User session data may include profile information, messages, personalized data and themes, recommendations, targeted promotions, and discounts.

Each user session has a unique identifier. Session data is never queried by anything other than a primary key, so a fast key-value store is a better fit for session data. In general, key-value databases may provide smaller per-page overhead than relational databases.