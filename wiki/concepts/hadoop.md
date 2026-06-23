---
concept: hadoop
entity_type: concept
aliases: []
sources: ["raw\\data_science_bigdata.md"]
confidence: high
created_at: 2026-06-23T04:12:38Z
---

## Definition

Hadoop is an open-source software framework that supports data-intensive distributed applications. It enables the processing of large data sets on clusters of commodity hardware. Hadoop is designed to scale up from single servers to thousands of machines, each offering local computation and storage. The core of Hadoop includes the Hadoop Distributed File System (HDFS) and MapReduce.

## How it Works

Hadoop operates using a distributed architecture, which means it processes data across multiple machines. The system architecture consists of the Hadoop Distributed File System (HDFS) and the MapReduce computational paradigm.

### Hadoop Distributed File System (HDFS)
hadoop-distributed-file-system
HDFS stores large files across multiple machines and operates on a "write once, read many" paradigm. Files are split into blocks, and typically these blocks are replicated for fault tolerance. In essence, HDFS distributed-file-system [[bigdata]] extends the capabilities of traditional file systems to manage and store petabytes of data efficiently. Each block of data is replicated across multiple nodes in the cluster to ensure fault tolerance and high availability.

### MapReduce
[[mapreduce]]
MapReduce is a software framework for easily writing applications that process vast amounts of data in parallel on large clusters of commodity hardware. The data processing jobs are split into multiple small tasks that are executed in parallel. This approach is not only efficient in managing large volumes of data, but also in processing data faster than traditional single-node methods. Each map job processes a portion of the input data and generates a set of intermediate key-value pairs. The reduce phase takes these intermediate key-value pairs and performs a final aggregation.

## Variants

Over time, several technologies have been developed to optimize or extend capabilities of the original Hadoop framework:

### Apache Spark
apache-spark
Apache Spark provides a big data processing framework that optimizes MapReduce, focusing on improvements in performance and scalability. It relies on Resilient Distributed Datasets (RDDs) and is optimized for in-memory processing to be faster than Hadoop MapReduce. Spark supports a wider range of workloads, including streaming data, machine learning, and graph processing, drastically reducing processing times. It builds on the distributed computing paradigm similar to Hadoop and distributed-computing, but with significant performance enhancements.

## Trade-offs

While Hadoop is a powerful tool for processing large datasets, it comes with a set of trade-offs and limitations. One of the major trade-offs lies in the speed of data processing. [[mapreduce]] operates by storing intermediate values on disk, which can slow down processing, especially for iterative algorithms. Furthermore, Hadoop's disk-centric approach does not capitalize on the speed of memory processing, which can be significantly faster.

Hadoop also requires careful consideration of how data is partitioned across nodes and managed for efficient read and write operations. Effective use of Hadoop often necessitates complex tuning and configuration, making it less straightforward than some other solutions. Additionally, Hadoop does not perform well with real-time data processing due to its batch-oriented model.