Tags: #ComputerScience #Databases 

Denormalization is a database optimization technique where redundant data is intentionally added to one or more tables to reduce the need for complex joins and improve query performance. It is not the opposite of normalization, but rather an optimization applied after normalization.
# Step 1: Unnormalized Table
This is the starting point, where all data is stored in a single table.

| StudentID | StudentName | ClassID | ClassName | TeacherName  | Subject   |
| --------- | ----------- | ------- | --------- | ------------ | --------- |
| 1         | Alice       | C101    | Math      | Mr. Smith    | Algebra   |
| 1         | Alice       | C101    | Math      | Mr. Smith    | Geometry  |
| 2         | Bob         | C102    | Science   | Mrs. Johnson | Physics   |
| 2         | Bob         | C102    | Science   | Mrs. Johnson | Chemistry |

- **Redundancy**: For example, Alice and Math are repeated multiple times. Similarly, Mr. Smith is stored twice for the same class.
- **Update Anomalies**: If Mrs. Smith changes to Mr.Brown, we have to update multiple rows. Missing one row could lead to inconsistencies.
- **Inefficient Storage**: Repeated information takes up unnecessary space.
# Step 2: Normalized Structure
To eliminate redundancy and avoid anomalies, we split the data into smaller, related tables. This process is called normalization. Each table now focuses on a specific aspect, such as students, classes or subjects.

| StudentID | StudentName |
| --------- | ----------- |
| 1         | Alice       |
| 2         | Bob         |

| ClassID | ClassName | TeacherName  |
| ------- | --------- | ------------ |
| C101    | Math      | Mr. Smith    |
| C102    | Science   | Mrs. Johnson |

| StudentID | ClassID |
| --------- | ------- |
| 1         | C101    |
| 2         | C102    |

| ClassID | Subject   |
| ------- | --------- |
| C101    | Algebra   |
| C101    | Geometry  |
| C102    | Physics   |
| C102    | Chemistry |

- **No Redundancy**: Mr. Smith appears only once in the classes table, even if multiple subjects are associated with the class.
- **Easier Updates**: If Mrs. Smith changes to Mr. Brown, you only have to update the classes table and it automatically reflects everywhere.
- **Efficient Storage**: Repeated data is eliminated, saving space.
# Step 3: Denormalized Table
In some cases, normalization can make querying complex and slow because you need to join multiple tables to get the required information. To optimize performance, we can denormalize the data by combining related tables into a single table.
- All related information is stored in a single table.
- This simplifies querying because you don't need to join multiple tables.

| StudentID | StudentName | ClassName | TeacherName  | Subject   |
| --------- | ----------- | --------- | ------------ | --------- |
| 1         | Alice       | Math      | Mr. Smith    | Algebra   |
| 1         | Alice       | Math      | Mr. Smith    | Geometry  |
| 2         | Bob         | Science   | Mrs. Johson  | Physics   |
| 2         | Bob         | Science   | Mrs. Johnson | Chemistry |
# References
## Articles
- [Denormalization in Databases](https://www.geeksforgeeks.org/dbms/denormalization-in-databases/)

[[Databases MOC]]