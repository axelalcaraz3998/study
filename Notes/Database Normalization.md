Tags: #ComputerScience #Databases 

Database normalization is the process of structuring a relational database in accordance with a series of normal forms to reduce data redundancy and improve data integrity. Normalization entails organizing the columns and tables of a database to ensure that their dependencies are properly enforced by database integrity constraints. It is accomplished by applying some formal rules either by a process of synthesis (creating a new database design) or decomposition (improving an existing database design).

The benefits of database normalization include:
- **Prevention of Data Anomalies**: When larger more complicated tables are decomposed into smaller, simple tables, altering a database becomes an easier, less error-prone process, and limits changes to the now smaller tables of related data.
- **Reduction of Unintentional Data Redundancy**: While intentional data redundancy can help improve data quality, security, and availability, unintentional data redundancy is the effect of systems inadvertently creating duplicate data, which results in inefficiencies.
- **Data Storage Cost Savings**: Reducing duplicate data through database normalization can lower data storage costs. This is specially important for cloud environments where pricing is often based on the volume of data storage used.
- **Faster Data Retrieval**: Less data redundancy due to normalization can also lead to faster data queries as lower redundancy often require less data processing during searches.
# Normal Forms
Executing normalization in data models involves designing tables to conform with one or more levels of normalization, also known as normal forms. Common forms include:
- First normal form (1NF).
- Second normal form (2NF).
- Third normal form (3NF).
- Boyce-Codd normal form (BCNF).
- Fourth normal form (4NF).
- Fifth normal form (5NF).
## First Normal Form
- Each table must have a primary key, which uniquely identifies each row.
- Each column in the table must contain atomic (indivisible) values.
- The values in each column must be of the same data type.

See [[First Normal Form (1NF)]].
## Second Normal Form
- The table must be 1NF.
- All non-key attributes (columns) must be fully functionality dependent on the entire primary key. This means that every non-key attribute must depend on the entire primary key, not just part of it.

See [[Second Normal Form (2NF)]].
## Third Normal Form
- The table must be in 2NF.
- There should be no transitive dependencies, meaning that non-key attributes should not depend on other non-key attributes.

See [[Third Normal Form (3NF)]].
## Boyce-Codd Normal Form
- The table must be in 3NF.
- Every non-key attribute must be functionally dependent on the superkey, which is any set of attributes that uniquely identifies a row.

See [[Boyce-Codd Normal Form (BCNF)]].
## Fourth Normal Form
- The table must be in BCNF.
- It deals with multi-valued dependencies, ensuring that no non-key attribute is dependent on other non-key attributes in a way that creates unnecessary duplication of data.

See [[Fourth Normal Form (4NF)]].
## Fifth Normal Form
- The table must be in 4NF.
- It addresses join dependencies, ensuring that tables are organized to minimize the need for complex join in queries.

See [[Fifth Normal Form (5NF)]].
# References
## Articles
- [Database normalization](https://en.wikipedia.org/wiki/Database_normalization)
- [What is database normalization?](https://www.ibm.com/think/topics/database-normalization)
## Videos
- [Learn Database Normalization - 1NF, 2NF, 3NF, 4NF, 5NF](https://www.youtube.com/watch?v=GFQaEYEc8_8)

[[Databases MOC]]