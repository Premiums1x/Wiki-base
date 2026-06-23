---
concept: hdfs
entity_type: technique
aliases: ["hadoop-distributed-file-system"]
sources: ["raw/data_science_bigdata.md"]
confidence: high
created_at: 2026-06-23T03:34:16Z
---

## Definition

HDFS, or Hadoop Distributed File System, is a distributed, scalable, and portable file system designed to store very large files across multiple machines. It is part of the Apache Hadoop ecosystem and is commonly used for big data storage due to its ability to efficiently distribute files across clusters of commodity hardware. HDFS is known for its high fault-tolerance, allowing for data recovery in case of hardware failures.

## How it Works

HDFS is designed to handle large datasets by splitting files into smaller blocks, typically 128 MB to 256 MB in size. Each block is distributed across multiple DataNodes in the cluster, and by default, three copies of each block are stored to ensure high availability and fault tolerance. The NameNode, a master node, manages the file system's namespace and controls access to files by clients. It keeps metadata in memory for quick read operations and on disk for recovery after a restart. When a client writes to an HDFS file, the data is initially buffered and then written to a dedicated DataNode, which sends acknowledgment to the NameNode. Upon receiving acknowledgments from enough DataNodes, the NameNode updates the metadata and returns a success to the client.

## Variants

- **Federated HDFS**: A variant of the standard HDFS setup that supports the deployment of multiple namespaces using separate NameNodes, enabling independent management and scaling of name-spaces.
- **High Availability (HA) HDFS**: Enforces high availability by using a “new active” protocol to avoid split-brain scenarios, utilizing a standby NameNode that takes over in case of the active NameNode's failure.
- **Erasure Coding**: An alternative to simple replication in distributed file systems that reduces storage overhead by encoding a given block of data into a larger set of blocks and storing only a subset of them for redundancy, effectively increasing fault tolerance while reducing storage requirements.

## Trade-offs

- **Storage Overhead**: HDFS's default replication strategy can result in a high storage overhead, as each file block is replicated three times by default.
- **Complexity**: The distributed nature of HDFS introduces complexity in managing a large cluster, including challenges in fault isolation and data recovery.
- **Performance Bottlenecks**: While designed for batch processing, HDFS might introduce latency due to the need for distributed file write transactions, making it less suitable for low-latency, interactive applications.
- **Bandwidth Consumption**: The replication of data across nodes can lead to significant network traffic, which can be a bottleneck in large clusters.
- **NameNode Limitations**: The NameNode is a single point of management and failure, requiring a complex mechanism for high availability using HDFS HA setup.

## See also

Data Science Lifecycle
MapReduce
[[apache-spark]]
RDD (Resilient Distributed Datasets)
Data Warehouse
Data Lake