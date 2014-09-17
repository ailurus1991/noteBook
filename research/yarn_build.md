**before**

	make install maven and protobuf and source the environment variables.

**file different**

	delete the newer file

**build from source**

	mvn package -Pdist -DskipTests -Dtar

**mosh replace the default ssh**

	mosh jzhou@craysun.cs.iit.edu --server=/home/jzhou/mosh_install/bin/mosh-server -p 10001

**make sure the internet**

# Learn note

	./hadoop-hdfs-project/hadoop-hdfs/src/main/java/org/apache/hadoop/hdfs/server/blockmanagement/BlockPlacementPolicyDefault.java = ReplicationTargetChooser.java
