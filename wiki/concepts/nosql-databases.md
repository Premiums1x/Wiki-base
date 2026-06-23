---
concept: nosql-databases
entity_type: concept
aliases: ["non-relational-databases"]
sources: ["raw/backend_roadmap.md"]
confidence: high
created_at: 2026-06-23T03:33:42Z
---

## Definition
NoSQL (short for "non SQL" or "non relational") databases are a type of database management system designed to handle and store unstructured or semi-structured data. Unlike traditional SQL databases that use tables and rows, NoSQL databases often use flexible schemas, allowing them to efficiently handle large volumes of diverse data.

## How it works
NoSQL databases utilize various data models such as document, column-family, key-value, and graph formats. These models offer a flexible data structure that supports high scalability and performance. Data in NoSQL databases can be accessed using APIs, programming languages, or a mix of both, enabling efficient data retrieval and storage. NoSQL databases prioritize horizontal scaling, which involves handling increased loads through the addition of more servers, in contrast to vertical scaling through more powerful servers.

### Key Characteristics
- **Schema-less or Flexible Schema**: NoSQL databases can adapt to changing data structures without the need for predefined schemas.
- **Horizontal Scalability**: Designed to scale out, not up, allowing the system to grow through distribution across multiple servers.
- **Eventual Consistency**: Data consistency is often managed for performance reasons, rather than enforcing rigid consistency as in ACID-compliant systems.
- **High Performance**: Optimized for operations that need speed, such as read-heavy and write-heavy applications.
- **Distributed Systems**: Many NoSQL databases can distribute data across multiple servers to maintain high availability and fault tolerance.

## Variants
### Document Stores
- **Examples**: MongoDB, Couchbase
- **Use Case**: Ideal for storing unstructured or semi-structured data. Documents are typically stored in JSON format.

### Key-Value Stores
- **Examples**: Redis, Amazon DynamoDB
- **Use Case**: Provide fast access and retrieval of data with simple key-value mapping, extremely useful in caching scenarios.

### Column-Family Stores
- **Examples**: Cassandra, Google Bigtable
- **Use Case**: Well-suited for applications that require high scalability and can distribute data across a large number of commodity servers.

### Graph Databases
- **Examples**: Neo4j, Amazon Neptune
- **Use Case**: Designed to store and query connected data efficiently, ideal for applications such as social networks, recommendation engines, and fraud detection.

## Trade-offs
### Advantages
- **Flexibility**: No fixed schema allows for easier adaptation of data structures.
- **Scalability**: Horizontal scaling capabilities support distributed systems and high transaction loads.
- **Performance**: Optimized for specific use cases such as high read or write operations.

### Disadvantages
- **Complexity**: Mechanisms to maintain data consistency are often distributed, leading to complexity in implementation.
- **Data Integrity**: NoSQL databases typically do not support ACID transactions, which can affect consistency and integrity in certain applications.
- **Query Flexibility**: Some NoSQL databases have less flexibility in querying compared to SQL databases, constraining complex data retrieval operations.

## See also
[[relational-databases]], Document Stores, Key-Value Stores, Column-Family Stores, Graph Databases, Schema Design, Horizontal Scaling, ACID Transactions, Eventual Consistency