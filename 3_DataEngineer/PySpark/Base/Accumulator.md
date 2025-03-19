[[PySpark]]
Accumulator variables are used for aggregating the information through associative and commutative operations. For example, you can use an accumulator for a sum operation or counters (in MapReduce). The following code block has the details of an Accumulator class for PySpark.

```python
class pyspark.Accumulator(aid, value, accum_param)
```

The following example shows how to use an Accumulator variable. An Accumulator variable has an attribute called value that is similar to what a broadcast variable has. It stores the data and is used to return the accumulator's value, but usable only in a driver program.

In this example, an accumulator variable is used by multiple workers and returns an accumulated value.
----------------------------------------accumulator.py-----------------------------------
```python
from pyspark import SparkContext 
sc = SparkContext("local", "Accumulator app") 
num = sc.accumulator(10) 
def f(x): 
   global num 
   num+=x 
rdd = sc.parallelize([20,30,40,50]) 
rdd.foreach(f) 
final = num.value 
print "Accumulated value is -> %i" % (final)
```
----------------------------------------accumulator.py-----------------------------------
**Output**
Accumulated value is -> 150