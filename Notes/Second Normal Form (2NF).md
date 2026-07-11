Tags: #ComputerScience #Databases 

2NF builds upon the foundation of 1NF and introduces a new requirement related to the relationship between non-key attributes and the primary key of a table. To achieve 2NF, a table must satisfy the following conditions:
- The table must already be in 1NF.
- All non-key attributes (columns) must be fully functionally dependent on the entire primary key. This means that every non-key attribute should depend on the entire primary key, not just part of it.
# Example
Continuing with the student and course example from 1NF:

| Student_ID | Student_name |
| ---------- | ------------ |
| 1          | Alice        |
| 2          | Bob          |
| 3          | Carol        |

| Student_ID | Course    |
| ---------- | --------- |
| 1          | Math      |
| 1          | Physics   |
| 1          | Chemistry |
| 2          | Biology   |
| 2          | History   |
| 3          | Math      |
| 3          | History   |

For this example to be in 2NF, the courses table should have a composite primary key of both *Student_ID* and *Course* columns. With this, the *Course* column depends on both parts of the primary key, which satisfies the requirements of 2NF. This design eliminates partial dependencies and ensures that each non-key attribute depends on the entire primary key.
# References
## Articles
- [Mastering database normalization: A comprehensive exploration of normal forms](https://www.researchgate.net/publication/374509386_Mastering_database_normalization_A_comprehensive_exploration_of_normal_forms)
## Videos
- [Learn Database Normalization - 1NF, 2NF, 3NF, 4NF, 5NF](https://www.youtube.com/watch?v=GFQaEYEc8_8)

[[Database Normalization]]