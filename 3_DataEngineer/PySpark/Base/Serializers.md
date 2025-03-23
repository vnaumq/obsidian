[[PySpark]]
Serialization is used for performance tuning on Apache Spark. All data that is sent over the network or written to the disk or persisted in the memory should be serialized. Serialization plays an important role in costly operations.

PySpark supports custom serializers for performance tuning. The following two serializers are supported by PySpark −

## MarshalSerializer

Serializes objects using Python’s Marshal Serializer. This serializer is faster than PickleSerializer, but supports fewer datatypes.

class pyspark.MarshalSerializer

## PickleSerializer

Serializes objects using Python’s Pickle Serializer. This serializer supports nearly any Python object, but may not be as fast as more specialized serializers.

class pyspark.PickleSerializer

Let us see an example on PySpark serialization. Here, we serialize the data using MarshalSerializer.

--------------------------------------serializing.py------------------------------------
```python
from pyspark.context import SparkContext
from pyspark.serializers import MarshalSerializer
sc = SparkContext("local", "serialization app", serializer = MarshalSerializer())
print(sc.parallelize(list(range(1000))).map(lambda x: 2 * x).take(10))
sc.stop()
```
--------------------------------------serializing.py------------------------------------
**Output** − The output of the above command is −

[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]