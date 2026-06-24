---
concept: relational-databases
entity_type: concept
aliases: []
sources: ["raw\\04-backend-development\\backend_roadmap.md"]
confidence: high
created_at: 2026-06-24T07:53:52Z
---

## Definition
A **relational database** is a type of database management system where data is structured in tables with predefined relationships between them. Each table represents a collection of records sharing a common structure, and the database provides efficient mechanisms for querying, updating, and managing these entities using [[sql]] queries. Relational databases are characterized by their ability to enforce data integrity and support complex transaction processing through the ACID properties.

## How it works
The conceptual structure of a relational database is defined by a relation or table, which consists of a header (columns) and body (rows). Each row, or record, represents an individual entity, while each column specifies the attribute of those entities. Columns typically have a defined data type and often adhere to specific constraints like primary keys or foreign keys. 

### Key Concepts
1. **Schema**: The schema of a relational database defines the tables, types of data stored, and the relationships between different tables. Schemas are rigid and add a layer of data integrity and normalization.
2. **ACID Properties**: Transactions in a relational database must be Atomic, Consistent, Isolated, and Durable. This ensures that data changes are completed fully (atomicity), do not leave the system in an inconsistent state (consistency), do not interfere with other transactions (isolation), and are permanently stored (durability).
3. **SQL Queries**: SQL is the standard language used to interact with relational databases, allowing users to query, manipulate, and manage the data stored in tables.
4. **Normalization**: The process of organizing data to minimize redundancy and dependency, which can help optimize performance and improve data integrity.
5. **Indexes and B+ Trees**: Indexes help speed up the access operations at the cost of additional storage but are crucial for performance optimization. B+ trees are a common indexing mechanism used inside databases for efficient record retrieval.

## Variants
Several implementations of relational databases exist, each optimized for specific use cases and scenarios:
- **MySQL**: Widely used for web applications due to its speed and ease of integration with various frameworks. It is known for its strong support for ACID transactions and robust security model.
- **PostgreSQL**: Extends traditional relational database design to support more complex query types and has strong reliability and data integrity checks.
- **SQLite**: A relational database management system contained in a C library. It is lightweight and poses minimal setup or administration overhead compared to traditional DBMSs.
- **Microsoft SQL Server**: A powerful relational database system designed for large-scale enterprises, offering advanced features like in-database machine learning and high availability configurations.

## Trade-offs
While relational databases excel in managing structured data and ensuring integrity through ACID compliance, they come with trade-offs:
- **Rigidity**: Data schemas must be strictly defined, making it less flexible for handling evolving data needs.
- **Performance Scaling**: Schema rigidity and transaction atomicity can make scaling more challenging, especially in scenarios requiring high write throughput or horizontal scalability.
- **Data Size**: As the amount of data grows, maintaining performance becomes increasingly difficult without significant investment in additional hardware and storage solutions.

Relational databases often trade off flexibility for strong consistency and integrity, which is crucial in finance-systems but may not be as necessary in systems that prioritize availability or performance over strict consistency.

## See also
- [[sql]] - the most widely used language for querying and managing relational databases.
- nosql - an alternative approach that trades some of the relational database's rigorous consistency and schema requirements for scalability and flexibility.