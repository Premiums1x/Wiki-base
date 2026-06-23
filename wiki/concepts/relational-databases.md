---
concept: relational-databases
entity_type: concept
aliases: ["sql-databases"]
sources: ["raw/backend_roadmap.md"]
confidence: high
created_at: 2026-06-23T03:33:49Z
---

## Definition

A relational database is a type of database that organizes data into one or more tables (or relations) of columns and rows, with each column representing an attribute (like name, address, etc.) and each row representing a single record. The data in relational databases adhere to a well-defined schema that includes constraints to ensure data integrity and consistency. This structure allows for the efficient querying, updating, and searching of data using the Structured Query Language (SQL).

## How it Works

Relational databases use a tabular structure where each table, also known as a relation, has a unique name and is structured with a defined set of columns and rows. Each column represents a different type of data (e.g., an attribute of the entity that the table describes), and each row represents a specific instance of that entity. The schema of a relational database defines the structure of these tables, the types of data that can be stored in each column, and any constraints and relationships between tables.

A fundamental feature of relational databases is the ability to define relationships between different tables through foreign keys. These relationships enable the database to link data from multiple tables in a meaningful way, facilitating complex queries and maintaining the integrity of the overall data structure.

Queries are executed against the database using SQL, a standard language that allows for the precise specification of what data to retrieve or manipulate. SQL supports operations such as selecting data from one or multiple tables (using JOIN operations), inserting new records, updating existing data, and deleting records.

## Variants

### Relational Database Management Systems (RDBMS)
Several variants of relational databases are available as part of different Relational Database Management Systems (RDBMS). These systems handle the administration and access of relational databases:

- **MySQL**: A widely used relational database that is known for its speed, reliability, and ease of use.
- **PostgreSQL**: A powerful, open-source relational database known for its robustness and extensibility.
- **Microsoft SQL Server**: A set of relational database management systems developed by Microsoft. It includes features such as full-text search, SQL Server Reporting Services, and SQL Server Analysis Services.
- **Oracle Database**: A multi-model database management system produced by Oracle Corporation. It includes features such as data warehousing, RDBMS, mixed database, and a robust transactional database engine.

## Trade-offs

### Advantages
- **Data Integrity**: Relational databases enforce data integrity through the use of constraints and ensure that data consistency is maintained across related tables.
- **Scalability**: Through techniques like indexing, partitioning, and replication, relational databases can handle large volumes of data and high transaction loads efficiently.
- **Flexibility**: SQL provides a powerful query language for complex data retrieval and manipulation.

### Disadvantages
- **Performance**: In a highly denormalized data structure, relational databases can suffer from performance hits, especially with complex JOIN operations.
- **Horizontal Scaling Limitations**: Traditional relational databases can find it challenging to scale horizontally (increase capacity by increasing the number of nodes) due to complexities in data distribution and maintaining data consistency across nodes.
- **Schema Rigidity**: The strict schema of relational databases can be inflexible for dynamic web applications where data requirements change frequently.

## See also

Node.js, Go (Golang), Java, Python, Rust, Non-relational Databases (NoSQL), [[redis]], RESTful API