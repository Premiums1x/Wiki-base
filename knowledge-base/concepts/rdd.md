---
concept: rdd
entity_type: concept
aliases: []
sources: ["raw\\02-data-science-and-bigdata\\data_science_bigdata.md"]
confidence: high
created_at: 2026-06-24T09:41:43Z
---

## Definition
RDD, or elastic-distributed-data-set, is a core concept within the Apache Spark distributed computing framework. RDDs represent large collections of elements that can be processed in parallel, and they are stored in memory to facilitate faster processing as compared to map-reduce, which often writes intermediate results to disk. RDDs extend the MapReduce paradigm by offering additional operations such as transformations and actions while maintaining strong consistency models and fault tolerance.

## How it works
RDDs are immutable collections of objects partitioned across nodes in a cluster and are designed for both in-memory and on-disk processing. An RDD has a collection of partitioned data and a task graph of operations that can be cached in memory and reused for multiple computations, which optimizes performance. There are two types of operations in RDD—the transformations (e.g., `map`, `filter`) which produce new RDDs, and actions (e.g., `count`, `collect`) which produce output but do not return new RDDs. Spark supports both coarse-grained tasks, which process many records, and fine-grained tasks, which process few records, making it flexible to different workloads.

RDDs manage data lineage, meaning if an RDD is lost, Spark can rebuild it from cache or disk due to its representation of each transformation as a chain of operations from the original data. This lineage information is critical for fault tolerance, allowing fault detection and recovery to occur without needing backups. Furthermore, Spark can partition data in various ways for parallelism and locality, and can shuffle data between partitions during transformations to ensure that each task processes the dataset across multiple partitions.

## Variants
Spark has evolved to include DataFrames and Datasets, enhancements over RDDs that offer type safety and optimizes execution plans using Catalyst optimizer. These are considered more high-level abstractions and alternatives compared to RDDs because they are easier to use while keeping the performance benefits of RDDs. They allow Spark to generate more efficient execution plans and improve execution time.

## Trade-offs
Although RDDs offer an immediate layer of abstraction over MapReduce operations and mean that work can be cached and reused more effectively, there are trade-offs. First, RDDs can be complex to use and understand for those not well-versed in parallel computing and the Spark framework. Second, maintaining lineage information can consume a significant amount of memory and processing power, especially for complex transformation chains. This could slow down the overall job execution time, depending on the size of the datasets and the number of transformations involved.

RDDs are also largely stateless, which means they do not maintain state across operations, which can be both a strength and a limitation. While this supports the framework's ability to run in a fault-tolerant manner without relying heavily on intermediate states, it requires programmers to manually manage state through transformations and actions—a task that may not align with high-level, stateful use cases, thus trading off flexibility with complexity.

## See also
- map-reduce
- elastic-distributed-data-set
- in-memory
- spark