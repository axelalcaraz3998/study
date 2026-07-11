Tags: #ComputerScience #Databases 

4NF is a further level of normalization that builds upon the concepts of 1NF, 2NF, 3NF, and BCNF. To achieve 4NF, a table must satisfy the following conditions:
- The table must already be in BCNF.
- It addresses multi-valued dependencies, ensuring that there are no non-trivial multi-valued dependencies among non-key attributes.

In simpler terms, 4NF ensures that there are no sets of non-key attributes that are functionally dependent on the primary key and exhibit multi-valued dependencies.
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

| Course    | Instructor  | Schedule  |
| --------- | ----------- | --------- |
| Math      | Dr. Smith   | MWF 9-10  |
| Physics   | Dr. Johnson | TTh 11-12 |
| Chemistry | Dr. Davis   | MWF 1-2   |
| Biology   | Dr. Wilson  | TTh 9-10  |
| History   | Dr. Clark   | MWF 3-4   |

In the 3NF and BCNF structures, there are no partial dependencies or functional dependencies that violate those normal forms. However, let's introduce a new requirement to demonstrate 4NF. Suppose we want to track additional information about the textbooks used in each course, including their titles and authors. Here's an example of a textbooks table:

| Course    | Textbook_Title       | Textbook_Author |
| --------- | -------------------- | --------------- |
| Math      | Calculus             | Dr. Johnson     |
| Physics   | Physics Fundamentals | Dr. Davis       |
| Chemistry | Chem Principles      | Dr. Smith       |
| Biology   | Biology 101          | Dr. Wilson      |
| History   | World History        | Dr. Clark       |

In this textbooks table, the *Course* column contains values that are functionally dependent on the primary key (i.e., the combination of *Course* and *Textbook_Title*). However, there is a multi-valued dependency between *Course* and *Textbook_Author* because a course can have multiple textbooks, each with its own author.

To bring this into 4NF, we need to create separate tables for courses, textbooks, and textbook authors while maintaining the relationship between them. Here's how the tables might look after applying 4NF:

| Course    | Textbook_Title       |
| --------- | -------------------- |
| Math      | Calculus             |
| Physics   | Physics Fundamentals |
| Chemistry | Chem Principles      |
| Biology   | Biology 101          |
| History   | World History        |

| Textbook_Title       | Textbook_Author |
| -------------------- | --------------- |
| Calculus             | Dr. Johnson     |
| Physics Fundamentals | Dr. Davis       |
| Chem Principles      | Dr. Smith       |
| Biology 101          | Dr. Wilson      |
| World History        | Dr. Clark       |

Now, the textbooks table is in 4NF. Each table has its own primary key, and there are no non-trivial multi-valued dependencies among non-key attributes. This separation allows us to maintain data integrity and avoid data redundancy while meeting the requirements of 4NF.
# References
## Articles
- [Mastering database normalization: A comprehensive exploration of normal forms](https://www.researchgate.net/publication/374509386_Mastering_database_normalization_A_comprehensive_exploration_of_normal_forms)
## Videos
- [Learn Database Normalization - 1NF, 2NF, 3NF, 4NF, 5NF](https://www.youtube.com/watch?v=GFQaEYEc8_8)

[[Database Normalization]]