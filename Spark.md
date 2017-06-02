# Deploy Mode - [Client Mode](https://spark.apache.org/docs/latest/submitting-applications.html)
A common deployment strategy is to submit your application from a gateway machine that is physically co-located with your worker machines (e.g. Master node in a standalone EC2 cluster). In this setup, client mode is appropriate. In client mode, the driver is launched directly within the spark-submit process which acts as a client to the cluster. The input and output of the application is attached to the console. Thus, this mode is especially suitable for applications that involve the REPL (e.g. Spark shell).
# Deploy Mode - [Cluster Mode](https://spark.apache.org/docs/2.1.0/cluster-overview.html)
![Diagram](https://spark.apache.org/docs/2.1.0/img/cluster-overview.png) 

Alternatively, if your application is submitted from a machine far from the worker machines (e.g. locally on your laptop), it is common to use cluster mode to minimize network latency between the drivers and the executors. Currently, standalone mode does not support cluster mode for Python applications.
