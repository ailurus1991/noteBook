#API

* old version: org.apache.hadoop.mapred
* new version: org.apache.hadoop.mapreduce

#Conf
System default config files: core-default.xml, hdfs-default.xml and mapred-default.xml
Administrator config files: core-site, hdfs-site and mapred-site, these files will replace the system defaults.

#ChainMapper/ChainReducer
Mapper likes the Linux pipe command.
In map phase, mapper1 -> mapper2 -> mapper3
In reduce phase, 

#Hadoop RPC
Just like a regular remote request, dont worry about the contract, no matter is the TCP or UDP.

#Compile
 
    ant -Document-core=true
