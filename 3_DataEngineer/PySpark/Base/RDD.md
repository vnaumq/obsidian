[[PySpark]]

**Resilient Distributed Dataset**

Now that we have installed and configured PySpark on our system, we can program in Python on Apache Spark. However before doing so, let us understand a fundamental concept in Spark - RDD.

RDD stands for **Resilient Distributed Dataset**, these are the elements that run and operate on multiple nodes to do parallel processing on a cluster. RDDs are immutable elements, which means once you create an RDD you cannot change it. RDDs are fault tolerant as well, hence in case of any failure, they recover automatically. You can apply multiple operations on these RDDs to achieve a certain task.

To apply operations on these RDD's, there are two ways −
- Transformation 
- Action

Let us understand these two ways in detail.

**Transformation** − These are the operations, which are applied on a RDD to create a new RDD. Filter, groupBy and map are the examples of transformations.

**Action** − These are the operations that are applied on RDD, which instructs Spark to perform computation and send the result back to the driver.

To apply any operation in PySpark, we need to create a **PySpark RDD** first. The following code block has the detail of a PySpark RDD Class −
```python
class pyspark.RDD (
   jrdd, 
   ctx, 
   jrdd_deserializer = AutoBatchedSerializer(PickleSerializer())
)
```
Let us see how to run a few basic operations using PySpark. The following code in a Python file creates RDD words, which stores a set of words mentioned.
```python
words = sc.parallelize (
   ["scala", 
   "java", 
   "hadoop", 
   "spark", 
   "akka",
   "spark vs hadoop", 
   "pyspark",
   "pyspark and spark"]
)
```
We will now run a few operations on words.
## count()

Number of elements in the RDD is returned.
----------------------------------------count.py---------------------------------------
```python
from pyspark import SparkContext
sc = SparkContext("local", "count app")
words = sc.parallelize (
   ["scala", 
   "java", 
   "hadoop", 
   "spark", 
   "akka",
   "spark vs hadoop", 
   "pyspark",
   "pyspark and spark"]
)
counts = words.count()
print "Number of elements in RDD -> %i" % (counts)
```
----------------------------------------count.py---------------------------------------
Number of elements in RDD → 8

## collect()
All the elements in the RDD are returned.

## foreach(f)
Returns only those elements which meet the condition of the function inside foreach. 

## filter(f)
A new RDD is returned containing the elements, which satisfies the function inside the filter. In the following example, we filter out the strings containing ''spark".

## map(f, preservesPartitioning = False)
A new RDD is returned by applying a function to each element in the RDD. 

## reduce(f)
After performing the specified commutative and associative binary operation, the element in the RDD is returned

## join(other, numPartitions = None)
It returns RDD with a pair of elements with the matching keys and all the values for that particular key.

## cache()
Persist this RDD with the default storage level (MEMORY_ONLY)

