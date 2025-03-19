[[PySpark]]

For parallel processing, Apache Spark uses shared variables. A copy of shared variable goes on each node of the cluster when the driver sends a task to the executor on the cluster, so that it can be used for performing tasks.

There are two types of shared variables supported by Apache Spark −

- Broadcast
- Accumulator

Let us understand them in detail.

## Broadcast

Broadcast variables are used to save the copy of data across all nodes. This variable is cached on all the machines and not sent on machines with tasks. The following code block has the details of a Broadcast class for PySpark.

```python
class pyspark.Broadcast (
   sc = None, 
   value = None, 
   pickle_registry = None, 
   path = None
)
```
The following example shows how to use a Broadcast variable. A Broadcast variable has an attribute called value, which stores the data and is used to return a broadcasted value.

----------------------------------------broadcast.py--------------------------------------
```python
from pyspark import SparkContext 
sc = SparkContext("local", "Broadcast app") 
words_new = sc.broadcast(["scala", "java", "hadoop", "spark", "akka"]) 
data = words_new.value 
print "Stored data -> %s" % (data) 
elem = words_new.value[2] 
print "Printing a particular element in RDD -> %s" % (elem)
```
----------------------------------------broadcast.py--------------------------------------

**Output**
Stored data -> [
   'scala',  
   'java', 
   'hadoop', 
   'spark', 
   'akka'
]
Printing a particular element in RDD -> hadoop