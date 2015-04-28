Redesign the whole architecture to present more intelligent recommendation adaptively.

Data Collection —\> Analyze —\> Machine Learning to recommend

# Data Collection
We can continue Hebo or other open-source log collection system with simple analysis.

# Whole Architecture
Application layer: **Bagle**( Pregal on Spark), **Shark**(Hive on Spark), **Streaming Spark**(Multimedia)

Computing Framework: **Spark**
- MapReduce
- RDD
- Functional Programming

# Resource Management
**Mesos**, **Local mode** and **Standalone**, **Amazon EC2**, **YARN**

# Distributed Environment
File System: **HDFS**
Storage: **Simple Storage Service** Amazon S3
Database: **HBase**

# Algorithm
**Learning to rank**: an normal implementation is Ranklib(umass) __not distributed__
**MLbase**: Distributed machine-learning system to implement different machine learning algorithm. Here maybe we can implement the basic **byes**, **GBRT** and **MART**. 
