# 🧠 SQL Cheat Sheet

A concise reference guide for mastering SQL — from basics to advanced queries.  
Perfect for developers, data analysts, and learners. 🚀  

---

## 🧩 Introduction to SQL

**SQL (Structured Query Language)** is used to manage and manipulate relational databases.  
It allows users to create, read, update, and delete (CRUD) data efficiently.


Example
```
SELECT * FROM employees;
```

---

## 📋 Data Types

| Category  | Example Types                   |
| --------- | ------------------------------- |
| Numeric   | INT, FLOAT, DECIMAL             |
| String    | CHAR, VARCHAR, TEXT             |
| Date/Time | DATE, TIME, DATETIME, TIMESTAMP |
| Boolean   | BOOLEAN, BIT                    |

---

## ⚙️ SQL Commands Overview

| Type | Commands                       | Description               |
| ---- | ------------------------------ | ------------------------- |
| DDL  | CREATE, ALTER, DROP, TRUNCATE  | Define database schema    |
| DML  | SELECT, INSERT, UPDATE, DELETE | Manage data within tables |
| DCL  | GRANT, REVOKE                  | Control permissions       |
| TCL  | COMMIT, ROLLBACK, SAVEPOINT    | Manage transactions       |

---

## 🧱 DDL – Data Definition Language

```
CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  salary DECIMAL(10, 2),
  hire_date DATE
);

ALTER TABLE employees ADD department VARCHAR(50);
DROP TABLE employees;
TRUNCATE TABLE employees;
```
---

## ✏️ DML – Data Manipulation Language

```
INSERT INTO employees (id, name, salary) VALUES (1, 'Adarsh', 75000);
UPDATE employees SET salary = 80000 WHERE id = 1;
DELETE FROM employees WHERE id = 1;

```
---

## 🔐 DCL – Data Control Language

```
GRANT SELECT, UPDATE ON employees TO user1;
REVOKE UPDATE ON employees FROM user1;

```
---

## 🔁 TCL – Transaction Control Language

```
BEGIN TRANSACTION;
UPDATE accounts SET balance = balance - 1000 WHERE id = 1;
UPDATE accounts SET balance = balance + 1000 WHERE id = 2;
COMMIT;

-- Or rollback if error
ROLLBACK;


```
---
## 🔍 SELECT Statement

```
SELECT name, salary FROM employees;
SELECT DISTINCT department FROM employees;
SELECT * FROM employees ORDER BY salary DESC;
SELECT * FROM employees LIMIT 5 OFFSET 10;

```
---
## 🎯 WHERE Clause & Operators
```
SELECT * FROM employees
WHERE salary > 50000
  AND department = 'Engineering'
  OR name LIKE 'A%';

```
### Common Operators:

=, !=, <, >, <=, >=, BETWEEN, IN, LIKE, IS NULL

--- 

## 🔗 JOINs

| Type       | Description                                    |
| ---------- | ---------------------------------------------- |
| INNER JOIN | Returns only matching rows                     |
| LEFT JOIN  | All rows from left + matching right            |
| RIGHT JOIN | All rows from right + matching left            |
| FULL JOIN  | All rows when there is a match in either table |

```
SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d ON e.department_id = d.id;
```

--- 

## 📊 GROUP BY & HAVING

```
SELECT department, COUNT(*) AS total
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```
----
## 🪞 Subqueries

```
SELECT name
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);

```
---

## 👁️ Views

```
CREATE VIEW high_salary AS
SELECT name, salary FROM employees WHERE salary > 90000;

SELECT * FROM high_salary;
DROP VIEW high_salary;

```
---

## ⚡ Indexes

```
CREATE INDEX idx_name ON employees(name);
DROP INDEX idx_name;
```
---
## 🧱 Constraints
| Constraint  | Description                   |
| ----------- | ----------------------------- |
| PRIMARY KEY | Unique & Not Null             |
| FOREIGN KEY | References another table      |
| UNIQUE      | Ensures unique values         |
| CHECK       | Validates a condition         |
| NOT NULL    | Ensures column cannot be null |

```
CREATE TABLE orders (
  id INT PRIMARY KEY,
  amount DECIMAL(10,2) CHECK (amount > 0),
  customer_id INT,
  FOREIGN KEY (customer_id) REFERENCES customers(id)
);

```
---
---
## 🧮 Useful Functions
| Category    | Examples                                                    |
| ----------- | ----------------------------------------------------------- |
| Aggregate   | `COUNT()`, `SUM()`, `AVG()`, `MAX()`, `MIN()`               |
| String      | `CONCAT()`, `LENGTH()`, `UPPER()`, `LOWER()`, `SUBSTRING()` |
| Date        | `NOW()`, `CURDATE()`, `YEAR()`, `MONTH()`                   |
| Conditional | `CASE WHEN THEN ELSE END`                                   |


```
SELECT name,
  CASE
    WHEN salary >= 90000 THEN 'High'
    WHEN salary >= 50000 THEN 'Medium'
    ELSE 'Low'
  END AS salary_level
FROM employees;

```
---
## 💡 Common SQL Interview Queries

### Find 2nd highest salary
```
SELECT MAX(salary) FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
```

### Count employees per department
```
SELECT department, COUNT(*) FROM employees GROUP BY department;
```

### Retrieve employees who joined in last 30 days
```
SELECT * FROM employees
WHERE hire_date >= CURDATE() - INTERVAL 30 DAY;
```
---

## 📚 References & Resources

📍 W3Schools SQL Tutorial

📍SQLBolt Interactive Lessons

📍Mode Analytics SQL Tutorial

📍 LeetCode SQL Practice

---

## 👨‍💻 Author

---
### Adarsh Lilhare 

🎓 B.Tech in Artificial Intelligence & Data Science

💼 AI & Data Science Student | 💻 Developer | 🌍 Open Source Contributor

📧 [Email](adarshlilhare@example.com)

🐙 [GitHub](https://github.com/AdarshVL) 

🌐 [Portfolio](https://adarshlilhare.dev)

🔗 [LinkedIn](https://www.linkedin.com/in/adarsh-lilhare-b98a91290/)

---



