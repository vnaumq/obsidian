[[PySpark]]

To run a Spark application on the local/cluster, you need to set a few configurations and parameters, this is what SparkConf helps with. It provides configurations to run a Spark application. The following code block has the details of a SparkConf class for PySpark.

```python
class pyspark.SparkConf (
   loadDefaults = True, 
   _jvm = None, 
   _jconf = None
)
```

Initially, we will create a SparkConf object with SparkConf(), which will load the values from **spark.*** Java system properties as well. Now you can set different parameters using the SparkConf object and their parameters will take priority over the system properties.

In a SparkConf class, there are setter methods, which support chaining. For example, you can write **conf.setAppName(“PySpark App”).setMaster(“local”)**. Once we pass a SparkConf object to Apache Spark, it cannot be modified by any user.

Following are some of the most commonly used attributes of SparkConf −

- **set(key, value)** − To set a configuration property.
    
- **setMaster(value)** − To set the master URL.
    
- **setAppName(value)** − To set an application name.
    
- **get(key, defaultValue=None)** − To get a configuration value of a key.
    
- **setSparkHome(value)** − To set Spark installation path on worker nodes.

Let us consider the following example of using SparkConf in a PySpark program. In this example, we are setting the spark application name as **PySpark App** and setting the master URL for a spark application to → **spark://master:7077**.

The following code block has the lines, when they get added in the Python file, it sets the basic configurations for running a PySpark application.

---------------------------------------------------------------------------------------
```python
from pyspark import SparkConf, SparkContext
conf = SparkConf().setAppName("PySpark App").setMaster("spark://master:7077")
sc = SparkContext(conf=conf)
```
---------------------------------------------------------------

