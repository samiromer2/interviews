questions 👍

SQL 
-- Suggested testing environment:
-- For MS SQL:
-- https://sqliteonline.com/ with language set as MS SQL
-- For PostgreSQL:
-- https://sqliteonline.com/ with language set as PostgreSQL
-- For MySQL:
-- https://www.db-fiddle.com/ with MySQL version set to 8
-- For SQLite:
-- http://sqlite.online/

-- Example case create statement:
CREATE TABLE employees (
   id INTEGER NOT NULL PRIMARY KEY,
   name VARCHAR(50) NOT NULL
);

CREATE TABLE sales (
   id INTEGER NOT NULL PRIMARY KEY,
   employeeId INT NOT NULL,
   amount INT NOT NULL,
   year INT NOT NULL,
   FOREIGN KEY (employeeId) REFERENCES employees(id)
);

INSERT INTO employees(id, name) values(0, 'Sarah');
INSERT INTO employees(id, name) values(1, 'Jack');
INSERT INTO employees(id, name) values(2, 'Angelina');

INSERT INTO sales(id, employeeId, amount, year) values(0, 0, 5000, 2023);
INSERT INTO sales(id, employeeId, amount, year) values(1, 0, 6000, 2024);
INSERT INTO sales(id, employeeId, amount, year) values(2, 1, 3000, 2024);

-- Insert answer here

write an sql , for all empleymees and there amounts 

including the angelina 

id -> totla


sol : 

SELECT e.id,
       e.name,
       COALESCE(SUM(s.amount), 0) AS total
FROM employees e
LEFT JOIN sales s ON e.id = s.employeeId
GROUP BY e.id, e.name
ORDER BY e.id;




NAV CANADA – Software Developer Interview Experience (2026)

The interview was mostly focused on problem-solving, SQL, algorithms, C++, and reasoning about existing code rather than trivia.

Questions I remember

1. SQL Query

Two tables were provided: Employees and EmployeeSales.
Write a query that returns all employees, including those who made no sales.
Show each employee along with their total sales, making sure employees without sales still appear in the result (using an appropriate join).

2. Recursive Function

Analyze a recursive function that calls itself with different values (for example, f(5) and f(3)), with an if condition controlling the recursion.
Determine the output and explain how the recursion works.

3. Scheduling / Assignment Problem

Given a table of employees and their availability, assign two employees to a new task starting in September and lasting about three weeks.
Consider existing assignments, employees who are already busy, vacations, and other constraints.
The interviewer was interested in the reasoning and approach rather than a single correct answer.

4. Feature Usage / Set Intersection

A product analytics question represented with overlapping circles (similar to a Venn diagram).
Multiple product features had usage percentages.
The task was to determine how many users use at least three features by reasoning about the intersections.

5. C++ Memory Management

A code snippet contained a memory leak.
Identify the problem and explain how to fix it using proper pointer and object lifetime management (constructors/destructors or smart pointers where appropriate).

6. C++ Constructors / Existing Code

You are given a class written by another developer.
Implement or correct the constructor and explain what happens when objects are created and destroyed.
Multiple-choice questions followed to test understanding of object construction and destruction.
Overall Impression

The interview emphasized practical software engineering skills instead of memorization. The questions covered SQL, recursion, logical reasoning, scheduling algorithms, set operations, and C++ memory management. It was a challenging interview that required explaining your thought process as much as producing the correct answer.


1 for git logic question 
1 for listening

