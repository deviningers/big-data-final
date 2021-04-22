# Final Project for Big Data Course
> by Devin Ingersoll
This project will demonstraight how to use pyspark to perform data processing on a file in order to tell a story using the data

## The data
I am pulling in a txt file of one of my favorite books [Neuromancer](https://archive.org/stream/NeuromancerWilliamGibson/Neuromancer%20-%20William%20Gibson_djvu.txt) by William Gibson from good old [archive.org](archive.org) (probably legal... right?). Becasue pulling this would include HTTP tags and such, I copied the text into a txt file within my repo. 

## Tools
- The code was written and tested using [Databricks Community Edition](https://community.cloud.databricks.com) (a free, web-based platform for working with spark in IPython type notebooks)
- To pull the data in and perform actions on it I am using a [Pyspark](https://spark.apache.org/docs/latest/api/python/index.html), a python interface for Apache Spark: an analytics engine for big data processing

### Code
1. First, import the data into python > databricks > spark using
```python
import urllib.request
urllib.request.urlretrieve("https://github.com/deviningers/big-data-final/neuro.txt" , "/tmp/neuro.txt")
dbutils.fs.mv("file:/tmp/neuro.txt", "dbfs:/data/neuro.txt")
txtRDD = sc.textFile("/data/neuro.txt", 3)  # change 3 to be any number of servers with a dataset copy
```
- flatmap
- filter
- map
- reduceByKey

## Results


#### Resources
- [Dr. Case's (Instructor) lesson repo](https://github.com/denisecase/starting-spark)
- [Neuromancer txt](https://archive.org/stream/NeuromancerWilliamGibson/Neuromancer%20-%20William%20Gibson_djvu.txt)
- [Pyspark Documentation](https://spark.apache.org/docs/latest/api/python/index.html)
- [Pyspark examples](https://spark.apache.org/examples.html)
