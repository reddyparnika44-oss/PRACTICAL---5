# SQL Practical 5 – Indexing in MySQL

## Aim

To understand and implement **indexes in MySQL** and observe their effect on query execution using the `EXPLAIN` statement.

## Description

This practical creates a `school_db` database containing a `students` table. Student records are inserted, and queries are executed to retrieve students based on their city.

An index is then created on the `city` column to improve the efficiency of queries that search for students from a particular city. The `EXPLAIN` statement is used before and after creating the index to examine the query execution plan.

## Database Structure

### Database

`school_db`

### Table

`students`

| Column         | Data Type   | Description       |
| -------------- | ----------- | ----------------- |
| `student_id`   | INT         | Primary key       |
| `student_name` | VARCHAR(50) | Student's name    |
| `age`          | INT         | Student's age     |
| `class`        | INT         | Student's class   |
| `section`      | CHAR(1)     | Student's section |
| `city`         | VARCHAR(50) | Student's city    |
| `marks`        | INT         | Student's marks   |

The table is created with `student_id` as the primary key.

## Operations Performed

1. Create the `school_db` database.
2. Select the database using `USE`.
3. Create the `students` table.
4. Insert 10 student records.
5. Display all student records.
6. Use `EXPLAIN` to analyze a query filtering students by city.
7. Create an index named `idx_student_city` on the `city` column.
8. Display the indexes using `SHOW INDEX`.
9. Use `EXPLAIN` again to analyze the query after indexing.
10. Retrieve students whose city is Nagpur.

## Index Created

```sql
CREATE INDEX idx_student_city
ON students(city);
```

The index `idx_student_city` is created on the `city` column.

## Query Used

```sql
SELECT * FROM students
WHERE city = 'Nagpur';
```

This query retrieves all students whose city is Nagpur.

## Purpose of EXPLAIN

`EXPLAIN` shows how MySQL plans to execute a query. In this practical, it is used to compare the query execution plan before and after creating an index on the `city` column.

## Expected Outcome

The practical demonstrates how an index can help MySQL efficiently search records based on a frequently queried column such as `city`.

## Conclusion

The practical successfully demonstrates the creation and use of an index in MySQL. The `EXPLAIN` command helps analyze the query execution plan, while the `idx_student_city` index is used to optimize searches based on the `city` column.
