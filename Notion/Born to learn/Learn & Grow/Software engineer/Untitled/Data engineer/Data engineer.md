---
Created: 2022-06-03T15:49
---
Network  
- OSI model

![[image 5.png|image 5.png]]

![[image 1 2.png|image 1 2.png]]

Data  
- datawarehouse, data lake, lakehouse.  
- avro schema  
- parquet  
- Glue crawler  
- ACID  
- Indexing  
- ETL vs ELT  
  
Hadoop: [https://www.youtube.com/watch?v=aReuLtY0YMI](https://www.youtube.com/watch?v=aReuLtY0YMI)  
- HDFS  
- MapReduce: Map (Distribute to node), Reduce (Combine the result)  
- YARN: a framework to provide computational resources for execution engines.  
  
Flink:  
- Serializable: transfer code to serializable type (binary) to push to node to execute.  
- Need data and code to get execution  
- Client will generate execution plan for JobManager  
  
Spark  
- Stream join  
- Windown  
- Spark struct streaming  
- Spark streaming mode (available_now, 0 minutes)  
  
Senarios:  
- Kafka lost message (retention.bytes from -1 to 0)  
- Kafka Streaming performance test (Team a Hạnh)  
- NRT Adobe MS1.  
  
Links  
[https://www.karanpratapsingh.com/courses/system-design  
](https://www.karanpratapsingh.com/courses/system-design)[https://www.educative.io/learn  
](https://www.educative.io/learn)[https://learn.cantrill.io/](https://learn.cantrill.io/)  
[https://www.educative.io/courses/distributed-systems-practitioners/q2KRowpo747](https://www.educative.io/courses/distributed-systems-practitioners/q2KRowpo747)