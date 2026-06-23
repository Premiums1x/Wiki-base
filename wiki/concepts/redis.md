---
concept: redis
entity_type: technique
aliases: []
sources: ["raw/backend_roadmap.md"]
confidence: high
created_at: 2026-06-23T03:33:44Z
---

## Definition
Redis is an in-memory data structure store used as a database, cache, and message broker. It supports various data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, hyperloglogs, and geospatial indexes with radius queries. Redis runs as a service that can persist data to disk, allowing for recovery in the event of a system failure.

## How it works
Redis operates as an in-memory database, which means it stores data in RAM for extremely fast read and write operations. It implements a key-value store where data is associated with keys; it supports multiple data types per key and provides commands to manipulate and query data of different types. Redis can be configured to persist data to disk either asynchronously (for performance) or synchronously (for durability). It also supports master-slave replication, enabling data replication across multiple instances for high availability and data redundancy.

Redis can function in multiple capacity modes, including:
- **Cache**: Redis is often used as a cache to reduce the load on databases by storing frequently accessed data in memory.
- **Data Store**: As a database, Redis can store both operational and analytics data, relying on in-memory storage for high-performance read/write operations.
- **Message Queue (Broker)**: Redis supports Pub/Sub messaging and can serve as a message broker in application architectures.

## Variants
Redis offers several editions and configurations:
- **Redis Open Source**: This is the free, open-source version of Redis available under the open-source BSD license.
- **Redis Stack**: An all-in-one data platform that includes RedisJSON, RedisTimeSeries, RedisBloom, RedisGears, RedisModules, and Redisearch, designed for multi-model data management.
- **Redis Insigh**: A monitoring platform that offers real-time analytics and insights into Redis data structures.

## Trade-offs
Key trade-offs, limitations, and considerations:
- **Storage Limitation**: Since Redis primarily operates in memory, the size of the database is limited by the amount of RAM available in the system.
- **Durability**: Although Redis has mechanisms for data persistence to disk, it is still vulnerable to data loss in case of a sudden power outage or other catastrophic failures.
- **Data Types**: While Redis supports various data types, some complex queries or join operations that are available in traditional relational databases are not supported natively and can be more complex to implement.
- **Cost**: As an in-memory solution, the cost of RAM can be a significant factor, especially in large deployments.

## See also
Node.js, NestJS, MongoDB, Go (Golang), Goroutines, Rust