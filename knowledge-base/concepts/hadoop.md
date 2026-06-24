---
concept: hadoop
entity_type: concept
aliases: []
sources: ["raw\\02-data-science-and-bigdata\\data_science_bigdata.md"]
confidence: high
created_at: 2026-06-24T07:55:19Z
---

## Definition
Apache Hadoop is a distributed computing framework that processes and stores large volumes of data across clusters of computers by utilizing a simple programming modality. It is wikilink to hadoop-distributed-file-system (HDFS) for distributed storage and [[mapreduce]] for distributed computation. Hadoop provides a high-throughput and fault-tolerant system, making it suitable for big data analytics and processing.

## How it works
The core components of Hadoop include HDFS for storing海量数据 and MapReduce for processing分布式计算. HDFS distributes files into blocks across multiple DataNodes, enabling data to be stored across an entire cluster of cheap servers. Each block is replicated across multiple nodes for fault tolerance. The redundancy across nodes helps prevent data loss in case any single node fails.

MapReduce processes data distributed across HDFS through two primary stages: Map and Reduce. In the Map stage, data is split into key-value pairs, and filter transformations are applied in parallel. The operation’s output then undergoes a Shuffling phase where the Hadoop framework organizes data by key. The Reduce phase then aggregates the data for each key, generating a final set of results. This process allows for the distributed handling of large volumes of data.

Hadoop also depends on underlying operating systems for task scheduling and resource management. NameNodes direct the actions of all the DataNodes, ensuring that data blocks are stored across nodes correctly. yarn is an optional component that improves resource management and task scheduling, optimizing cluster resource utilization. 

Variants of distributed computing, such as [[spark]], extend Hadoop’s initial concepts by incorporating advancements like in-memory computing, and optimizations in performance and memory usage. These advancements often improve upon Hadoop's speed and efficiency. However, while Hadoop was designed primarily for batch processing, these newer frameworks provide real-time processing capabilities.

## Variants
While MapReduce and HDFS are foundational to Hadoop, several frameworks build on or optimize these concepts:
- **Apache Spark** improves upon the MapReduce framework by incorporating in-memory computation, significantly reducing processing time through RDDs (Resilient Distributed Datasets). Thus, Spark is faster than MapReduce in many use cases.
- **Apache Flink** is an open-source stream processing framework and engine for stateful computations over unbounded and bounded data streams. It is also an alternative to Hadoop for processing real-time data streams.
- **Apache Storm** is another real-time processing framework that extends MapReduce’s batch processing capabilities, focusing on real-time stream processing.

## Trade-offs
Hadoop's design requires a distributed computing environment and significant overhead for distributed data management, making it more complex and resource-intensive than single-machine processing. While Hadoop provides a robust fault-tolerance mechanism with data replication, this also leads to increased storage and network traffic. Additionally, the initial setup and maintenance of Hadoop clusters can be challenging and time-consuming. This complexity introduces higher operational costs and demands specialized expertise. Despite offering better scalability and fault tolerance for big data workloads, these advantages come at the cost of higher complexity and resource consumption compared to other, less scalable solutions.



## See also
- [[data-warehouse]]
- [[spark]]
- stream-processing
- [[data-lake]]