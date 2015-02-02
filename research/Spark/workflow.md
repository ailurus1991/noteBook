For any spark computation, we will first create a SparkConf object and use it to create a SparkContext object. We only need to configure the executor memory allocation and give the program name, to identify it in the Spark's web UI. **In local mode, the web UI can be access at __localhost:4040__ during the execution of a program**.

Use the SparkContext to read in ratings, which contains the rating file with "::" as the delimiter. The code parses each line to create a RDD for ratings that contains **(Int, Rating)** paris.


