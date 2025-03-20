In Apache Spark, you can upload your files using **sc.addFile** (sc is your default SparkContext) and get the path on a worker using **SparkFiles.get**. Thus, SparkFiles resolve the paths to files added through **SparkContext.addFile()**.

SparkFiles contain the following classmethods −

- get(filename)
- getrootdirectory()

Let us understand them in detail.

## get(filename)

It specifies the path of the file that is added through SparkContext.addFile().

## getrootdirectory()

It specifies the path to the root directory, which contains the file that is added through the SparkContext.addFile().

----------------------------------------sparkfile.py-----------------------------------
```python
from pyspark import SparkContext
from pyspark import SparkFiles
finddistance = "/home/hadoop/examples_pyspark/finddistance.R"
finddistancename = "finddistance.R"
sc = SparkContext("local", "SparkFile App")
sc.addFile(finddistance)
print "Absolute Path -> %s" % SparkFiles.get(finddistancename)
```
----------------------------------------sparkfile.py-----------------------------------

**Output** − The output for the above command is −

Absolute Path -> 
   /tmp/spark-f1170149-af01-4620-9805-f61c85fecee4/userFiles-641dfd0f-240b-4264-a650-4e06e7a5
   