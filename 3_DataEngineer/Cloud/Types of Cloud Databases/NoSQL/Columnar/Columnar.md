[[NoSQL]]

The Columnar Data Model of NoSQL is important. NoSQL databases are different from SQL databases. This is because it uses a data model that has a different structure than the previously followed row-and-column table model used with relational database management systems ([[RDBMS]]). [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) databases are a flexible schema model which is designed to scale horizontally across many servers and is used in large volumes of data.

### **Columnar Data Model of NoSQL :** 

Basically, the relational database stores data in rows and also reads the data row by row, column store is organized as a set of columns. So if someone wants to run analytics on a small number of columns, one can read those columns directly without consuming memory with the unwanted data. Columns are somehow are of the same type and gain from more efficient compression, which makes reads faster than before. Examples of Columnar Data Model: Cassandra and Apache Hadoop Hbase.

### **Working of Columnar Data Model:** 

In Columnar Data Model instead of organizing information into rows, it does in columns. This makes them function the same way that tables work in relational databases. This type of data model is much more flexible obviously because it is a type of NoSQL database. The below example will help in understanding the Columnar data model:

**Row-Oriented Table:**

|S.No.|Name|Course|Branch|ID|
|---|---|---|---|---|
|01.|Tanmay|B-Tech|Computer|2|
|02.|Abhishek|B-Tech|Electronics|5|
|03.|Samriddha|B-Tech|IT|7|
|04.|Aditi|B-Tech|E & TC|8|
**Column – Oriented Table:**

|S.No.|Name|ID|
|---|---|---|
|01.|Tanmay|2|
|02.|Abhishek|5|
|03.|Samriddha|7|
|04.|Aditi|8|

|S.No.|Course|ID|
|---|---|---|
|01.|B-Tech|2|
|02.|B-Tech|5|
|03.|B-Tech|7|
|04.|B-Tech|8|

|S.No.|Branch|ID|
|---|---|---|
|01.|Computer|2|
|02.|Electronics|5|
|03.|IT|7|
|04.|E & TC|8|

Columnar Data Model uses the concept of keyspace, which is like a schema in relational models.

### **Advantages of Columnar Data Model :**

- **Well structured:** Since these data models are good at compression so these are very structured or well organized in terms of storage.
- **Flexibility:** A large amount of flexibility as it is not necessary for the columns to look like each other, which means one can add new and different columns without disrupting the whole database
- **Aggregation queries are fast:** The most important thing is aggregation queries are quite fast because a majority of the information is stored in a column. An example would be Adding up the total number of students enrolled in one year.
- **Scalability:** It can be spread across large clusters of machines, even numbering in thousands.
- **Load Times:** Since one can easily load a row table in a few seconds so load times are nearly excellent.

### **Disadvantages of Columnar Data Model:**

- **Designing indexing Schema:** To design an effective and working schema is too difficult and very time-consuming.
- **Suboptimal data loading:** incremental data loading is suboptimal and must be avoided, but this might not be an issue for some users.
- **Security vulnerabilities:** If security is one of the priorities then it must be known that the Columnar data model lacks inbuilt security features in this case, one must look into relational databases.
- **Online Transaction Processing (OLTP):** Online Transaction Processing (OLTP) applications are also not compatible with columnar data models because of the way data is stored.