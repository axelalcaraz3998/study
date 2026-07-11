Tags: #ComputerScience #Databases 

1NF is the fundamental step in database normalization. To meet the requirements of 1NF, a table must satisfy the following criteria:
- **Unique Rows**: Each row in the table must be unique, meaning there should be a way to distinguish one row from another. This requirement is typically fulfilled by having a primary key, which is a column (or combination of columns) with unique values for each row.
- **Atomic Values**: Each column in the table should contain atomic (indivisible) values. In other words, a column should not contain multiple values or complex data types. It should only hold simple, single-valued data.
- **Homogeneous Data Types**: All values in a column should have the same data type. For example, if you have a column for age, all values in that column should be numeric integers.
# Example
Consider a table that stores information about students and their courses. Here's an example of a table that violates 1NF:

| Student_ID | Student_Name | Courses                  |
| ---------- | ------------ | ------------------------ |
| 1          | Alice        | Math, Physics, Chemistry |
| 2          | Bob          | Biology, History         |
| 3          | Carol        | Math, History            |

In this example:
- **Unique Rows**: The rows are unique because each row has a distinct *Student_ID*.
- **Atomic Values**: The *Courses* column violates 1NF because it contains multiple values. This column should only contain atomic values.
To bring this table into 1NF, the *Courses* column can be split into separate rows for each course, creating a new table for courses:

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

Now, both tables are in 1NF. The *Courses* column in the original table was non-atomic and had to be split into separate rows in the courses table to meet the 1NF requirements. This separation allows for more efficient data storage and querying while maintaining data integrity.
# References
## Articles
- [Mastering database normalization: A comprehensive exploration of normal forms](https://www.researchgate.net/publication/374509386_Mastering_database_normalization_A_comprehensive_exploration_of_normal_forms)
## Videos
- [Learn Database Normalization - 1NF, 2NF, 3NF, 4NF, 5NF](https://www.youtube.com/watch?v=GFQaEYEc8_8)

[[Database Normalization]]