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