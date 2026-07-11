Tags: #ComputerScience #Databases 

3NF is the next step in the process of database normalization. To achieve 3NF, a table must satisfy the following conditions:
- The table must already be in 2NF.
- There should be no transitive dependencies, meaning that non-key attributes should not depend on other non-key attributes.

In simpler terms, 3NF ensures that data is organized in a way that prevents redundant storage of information related to non-key attributes.
# Example
Continuing with the student and course registration example from the previous normal forms:

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

If we wanted to store additional information about the courses, such as the course instructor and the course schedule we would need to create a new course details table, linking it to the courses table through the *Course* column.

| Course    | Instructor  | Schedule  |
| --------- | ----------- | --------- |
| Math      | Dr. Smith   | MWF 9-10  |
| Physics   | Dr. Johnson | TTh 11-12 |
| Chemistry | Dr. Davis   | MWF 1-2   |
| Biology   | Dr. Wilson  | TTh 9-10  |
| History   | Dr. Clark   | MWF 3-4   |

With this, the *Course* column in the courses table is solely responsible for identifying the course, and the course detail table contains information about courses, satisfying he requirements of 3NF. This normalization ensures that there are no transitive dependencies among non-key attributes.
# References
## Articles
- [Mastering database normalization: A comprehensive exploration of normal forms](https://www.researchgate.net/publication/374509386_Mastering_database_normalization_A_comprehensive_exploration_of_normal_forms)
## Videos
- [Learn Database Normalization - 1NF, 2NF, 3NF, 4NF, 5NF](https://www.youtube.com/watch?v=GFQaEYEc8_8)

[[Database Normalization]]