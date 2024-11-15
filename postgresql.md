# PostgreSQL Cheat Sheet

## Table of Contents
1. [Data Definition](#data-definition)
2. [Data Manipulation](#data-manipulation)
3. [Data Querying](#data-querying)
4. [Data Control](#data-control)
5. [Transactions](#transactions)
6. [Indexes](#indexes)
7. [Test Data](#test-data)

## Data Definition

### Create a database
```sql
CREATE DATABASE database_name;
```

### Create a table
```sql
CREATE TABLE table_name (
    column1 datatype1 constraints,
    column2 datatype2 constraints,
    ...
);
```

### Alter a table
```sql
ALTER TABLE table_name ADD COLUMN new_column datatype;
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name ALTER COLUMN column_name TYPE new_datatype;
```

### Drop a table
```sql
DROP TABLE table_name;
```

## Data Manipulation

### Insert data
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

### Update data
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### Delete data
```sql
DELETE FROM table_name WHERE condition;
```

## Data Querying

### Basic SELECT
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition
ORDER BY column1 [ASC|DESC]
LIMIT n;
```

### JOIN
```sql
SELECT t1.column1, t2.column2
FROM table1 t1
INNER JOIN table2 t2 ON t1.column = t2.column;
```

### Aggregate functions
```sql
SELECT COUNT(*), AVG(column_name), SUM(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

### Subqueries
```sql
SELECT column_name
FROM table_name
WHERE column_name IN (SELECT column_name FROM another_table WHERE condition);
```

## Data Control

### Create user
```sql
CREATE USER username WITH PASSWORD 'password';
```

### Grant privileges
```sql
GRANT privilege ON table_name TO username;
```

### Revoke privileges
```sql
REVOKE privilege ON table_name FROM username;
```

## Transactions

### Begin a transaction
```sql
BEGIN;
```

### Commit a transaction
```sql
COMMIT;
```

### Rollback a transaction
```sql
ROLLBACK;
```

## Indexes

### Create an index
```sql
CREATE INDEX index_name ON table_name (column_name);
```

### Drop an index
```sql
DROP INDEX index_name;
```

## Test Data

Here's some example synthetic test data to practice the SQL commands:

```sql
-- Create tables
CREATE TABLE departments (
    dept_id SERIAL PRIMARY KEY,
    dept_name VARCHAR(50) NOT NULL
);

CREATE TABLE employees (
    emp_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    hire_date DATE NOT NULL,
    salary NUMERIC(10, 2) NOT NULL,
    dept_id INTEGER REFERENCES departments(dept_id)
);

-- Insert test data
INSERT INTO departments (dept_name) VALUES
('Human Resources'),
('Marketing'),
('Engineering'),
('Sales');

INSERT INTO employees (first_name, last_name, email, hire_date, salary, dept_id) VALUES
('John', 'Doe', 'john.doe@example.com', '2020-01-15', 60000.00, 1),
('Jane', 'Smith', 'jane.smith@example.com', '2019-05-20', 65000.00, 2),
('Mike', 'Johnson', 'mike.johnson@example.com', '2021-03-10', 75000.00, 3),
('Emily', 'Brown', 'emily.brown@example.com', '2018-11-01', 72000.00, 4),
('David', 'Lee', 'david.lee@example.com', '2022-07-05', 68000.00, 3);

-- Example queries to practice
-- 1. Select all employees
SELECT * FROM employees;

-- 2. Select employees with salary greater than 70000
SELECT first_name, last_name, salary FROM employees WHERE salary > 70000;

-- 3. Join employees with departments
SELECT e.first_name, e.last_name, d.dept_name
FROM employees e
JOIN departments d ON e.dept_id = d.dept_id;

-- 4. Count employees by department
SELECT d.dept_name, COUNT(*) as employee_count
FROM employees e
JOIN departments d ON e.dept_id = d.dept_id
GROUP BY d.dept_name;

-- 5. Update an employee's salary
UPDATE employees SET salary = 70000 WHERE emp_id = 1;

-- 6. Delete an employee
DELETE FROM employees WHERE emp_id = 5;
```

You can copy and paste these commands into your PostgreSQL client to create the tables and insert the test data. Then, you can practice using the various SQL commands from the cheat sheet on this data.

## Joins in SQL

Joins are used to combine rows from two or more tables based on a related column between them. Here are the main types of joins in SQL:

1. INNER JOIN
2. LEFT (OUTER) JOIN
3. RIGHT (OUTER) JOIN
4. FULL (OUTER) JOIN
5. CROSS JOIN
6. SELF JOIN

Let's add some more test data to illustrate these joins better:

```sql
-- Add more departments
INSERT INTO departments (dept_name) VALUES
('Finance'),
('IT Support');

-- Add more employees
INSERT INTO employees (first_name, last_name, email, hire_date, salary, dept_id) VALUES
('Sarah', 'Wilson', 'sarah.wilson@example.com', '2019-08-01', 62000.00, 5),
('Tom', 'Davis', 'tom.davis@example.com', '2020-11-15', 59000.00, 6),
('Emma', 'Taylor', 'emma.taylor@example.com', '2021-02-28', 71000.00, 2);

-- Create a new table for projects
CREATE TABLE projects (
    project_id SERIAL PRIMARY KEY,
    project_name VARCHAR(100) NOT NULL,
    start_date DATE,
    end_date DATE,
    dept_id INTEGER REFERENCES departments(dept_id)
);

-- Insert some projects
INSERT INTO projects (project_name, start_date, end_date, dept_id) VALUES
('Website Redesign', '2023-01-01', '2023-06-30', 2),
('ERP Implementation', '2023-03-01', '2024-02-29', 3),
('Employee Training Program', '2023-05-01', '2023-12-31', 1),
('Sales Automation', '2023-07-01', '2024-06-30', 4),
('Data Center Upgrade', '2023-09-01', '2024-03-31', 6);
```

Now, let's explore each type of join with examples:

### 1. INNER JOIN

INNER JOIN returns only the rows that have matching values in both tables.

```sql
-- Get all employees with their department names
SELECT e.first_name, e.last_name, d.dept_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.dept_id;
```

### 2. LEFT (OUTER) JOIN

LEFT JOIN returns all rows from the left table and the matched rows from the right table. If there's no match, NULL values are returned for columns from the right table.

```sql
-- Get all departments and their employees (if any)
SELECT d.dept_name, e.first_name, e.last_name
FROM departments d
LEFT JOIN employees e ON d.dept_id = e.dept_id;
```

### 3. RIGHT (OUTER) JOIN

RIGHT JOIN is similar to LEFT JOIN, but returns all rows from the right table and the matched rows from the left table.

```sql
-- Get all employees and their projects (if any)
SELECT e.first_name, e.last_name, p.project_name
FROM employees e
RIGHT JOIN projects p ON e.dept_id = p.dept_id;
```

### 4. FULL (OUTER) JOIN

FULL JOIN returns all rows when there's a match in either the left or right table.

```sql
-- Get all departments and all projects, showing matches where they exist
SELECT d.dept_name, p.project_name
FROM departments d
FULL JOIN projects p ON d.dept_id = p.dept_id;
```

### 5. CROSS JOIN

CROSS JOIN returns the Cartesian product of both tables (i.e., all possible combinations of rows).

```sql
-- Get all possible combinations of employees and projects
SELECT e.first_name, e.last_name, p.project_name
FROM employees e
CROSS JOIN projects p
LIMIT 10; -- Limiting to 10 rows for brevity
```

### 6. SELF JOIN

A SELF JOIN is used to join a table with itself. This is useful when you have hierarchical or related data within the same table.

Let's add a 'manager_id' column to our employees table to demonstrate this:

```sql
-- Add manager_id column
ALTER TABLE employees ADD COLUMN manager_id INTEGER REFERENCES employees(emp_id);

-- Update some employees with manager_id
UPDATE employees SET manager_id = 1 WHERE emp_id IN (2, 3);
UPDATE employees SET manager_id = 4 WHERE emp_id IN (5, 6, 7);

-- Self join to get employees and their managers
SELECT e.first_name AS employee_first_name, e.last_name AS employee_last_name,
       m.first_name AS manager_first_name, m.last_name AS manager_last_name
FROM employees e
LEFT JOIN employees m ON e.manager_id = m.emp_id;
```

### Combining Multiple Joins

You can also combine multiple joins in a single query:

```sql
-- Get employees, their departments, and their projects
SELECT e.first_name, e.last_name, d.dept_name, p.project_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.dept_id
LEFT JOIN projects p ON d.dept_id = p.dept_id;
```

These examples demonstrate the various types of joins in SQL and how they can be used with our test data. Remember that the choice of join type depends on your specific data requirements and the relationship between your tables.

# PostgreSQL Data Dump and Restore Cheat Sheet

This cheat sheet covers commands for dumping (exporting) and restoring (importing) data in PostgreSQL, including full database dumps and specific table dumps.

## Dumping Data

### Full Database Dump

To dump an entire database:

```bash
pg_dump dbname > outfile
```

Options:
- `-F c|d|t|p` output file format (custom, directory, tar, plain text)
- `-Z 0-9` compression level for compressed formats

Example (compressed custom format):
```bash
pg_dump -Fc mydb > mydb.dump
```

### Dumping Specific Tables

To dump specific tables:

```bash
pg_dump -t table1 -t table2 dbname > outfile
```

Example:
```bash
pg_dump -t employees -t departments mydb > tables_dump.sql
```

### Dumping Schema Only

To dump only the database schema (no data):

```bash
pg_dump -s dbname > schema.sql
```

### Dumping Data Only

To dump only the data (no schema):

```bash
pg_dump -a dbname > data.sql
```

## Restoring Data

### Restoring a Full Database

For plain text dumps:
```bash
psql dbname < infile
```

For custom or compressed formats:
```bash
pg_restore -d dbname infile
```

Example:
```bash
pg_restore -d mydb mydb.dump
```

### Restoring Specific Tables

Restore specific tables from a dump file:

```bash
pg_restore -d dbname --table=table1 --table=table2 infile
```

Example:
```bash
pg_restore -d mydb --table=employees --table=departments tables_dump.sql
```

## Additional Useful Commands

### List Contents of a Dump File

To list the contents of a dump file:

```bash
pg_restore -l infile
```

### Custom Format with Compression

Create a compressed custom-format dump:

```bash
pg_dump -Fc dbname > dbname.custom
```

### Parallel Dump and Restore

For faster operations on multi-processor machines:

Dump:
```bash
pg_dump -j num_of_jobs -Fd dbname -f out_directory
```

Restore:
```bash
pg_restore -j num_of_jobs -d dbname dump_directory
```

### Handling Large Databases

For very large databases, you might want to use the `-F d` (directory format) option:

```bash
pg_dump -Fd dbname -f out_directory
```

This creates a directory with one file per table, allowing you to selectively restore tables.

## Important Notes

1. Always ensure you have sufficient permissions to read from or write to the specified locations.
2. For production databases, it's often wise to use `-c` (clean) and `-C` (create) options when restoring to ensure a fresh state.
3. The `pg_dumpall` utility can be used to back up an entire PostgreSQL cluster, including role and tablespace definitions.
4. When dumping from one PostgreSQL version and restoring to another, use pg_dump from the higher version number.

Remember to replace `dbname`, `table1`, `table2`, `infile`, and `outfile` with your actual database names, table names, and file paths as appropriate.

# PL/pgSQL Tutorial and Cheat Sheet for PostgreSQL

PL/pgSQL (Procedural Language/PostgreSQL) is PostgreSQL's procedural programming language. It allows you to create functions, stored procedures, triggers, and more.

## Table of Contents
1. [Basic Structure](#basic-structure)
2. [Variables and Data Types](#variables-and-data-types)
3. [Control Structures](#control-structures)
4. [Cursors](#cursors)
5. [Functions](#functions)
6. [Stored Procedures](#stored-procedures)
7. [Triggers](#triggers)
8. [Exception Handling](#exception-handling)
9. [Example Data and Practices](#example-data-and-practices)

## Basic Structure

A basic PL/pgSQL block looks like this:

```sql
DO $$
DECLARE
    -- Variable declarations
BEGIN
    -- Code
EXCEPTION
    -- Exception handling
END $$;
```

## Variables and Data Types

Declare variables at the beginning of a block:

```sql
DECLARE
    first_name VARCHAR(50);
    employee_count INTEGER;
    hire_date DATE;
    is_active BOOLEAN;
```

## Control Structures

### IF-THEN-ELSE

```sql
IF condition THEN
    -- statements;
ELSIF condition THEN
    -- statements;
ELSE
    -- statements;
END IF;
```

### CASE

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ELSE result3
END CASE;
```

### Loops

```sql
-- Basic loop
LOOP
    -- statements;
    EXIT WHEN condition;
END LOOP;

-- For loop
FOR i IN 1..10 LOOP
    -- statements;
END LOOP;

-- While loop
WHILE condition LOOP
    -- statements;
END LOOP;
```

## Cursors

Cursors allow you to iterate over a result set:

```sql
DECLARE
    cur CURSOR FOR SELECT * FROM employees;
    emp RECORD;
BEGIN
    OPEN cur;
    LOOP
        FETCH cur INTO emp;
        EXIT WHEN NOT FOUND;
        -- Process emp record
    END LOOP;
    CLOSE cur;
END;
```

## Functions

Creating a function:

```sql
CREATE OR REPLACE FUNCTION func_name(param1 TYPE, param2 TYPE)
RETURNS return_type AS $$
DECLARE
    -- Variable declarations
BEGIN
    -- Function body
    RETURN value;
END;
$$ LANGUAGE plpgsql;
```

## Stored Procedures

Creating a stored procedure (PostgreSQL 11+):

```sql
CREATE OR REPLACE PROCEDURE proc_name(param1 TYPE, param2 TYPE)
LANGUAGE plpgsql
AS $$
BEGIN
    -- Procedure body
END;
$$;
```

## Triggers

Creating a trigger:

```sql
CREATE TRIGGER trigger_name
{BEFORE | AFTER} {INSERT | UPDATE | DELETE} ON table_name
FOR EACH ROW
EXECUTE FUNCTION trigger_function();
```

## Exception Handling

```sql
BEGIN
    -- Code that might raise an exception
EXCEPTION
    WHEN condition THEN
        -- Handle the exception
    WHEN OTHERS THEN
        -- Handle other exceptions
END;
```

## Example Data and Practices

Let's create some example data and practice PL/pgSQL:

```sql
-- Create tables
CREATE TABLE departments (
    dept_id SERIAL PRIMARY KEY,
    dept_name VARCHAR(100) NOT NULL
);

CREATE TABLE employees (
    emp_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    hire_date DATE NOT NULL,
    salary NUMERIC(10, 2) NOT NULL,
    dept_id INTEGER REFERENCES departments(dept_id)
);

-- Insert sample data
INSERT INTO departments (dept_name) VALUES
('HR'), ('IT'), ('Sales'), ('Marketing');

INSERT INTO employees (first_name, last_name, email, hire_date, salary, dept_id) VALUES
('John', 'Doe', 'john.doe@example.com', '2020-01-15', 60000, 1),
('Jane', 'Smith', 'jane.smith@example.com', '2019-05-20', 65000, 2),
('Mike', 'Johnson', 'mike.johnson@example.com', '2021-03-10', 55000, 3),
('Emily', 'Brown', 'emily.brown@example.com', '2018-11-01', 70000, 4);

-- Function to get employee count by department
CREATE OR REPLACE FUNCTION get_employee_count(dept_id_param INTEGER)
RETURNS INTEGER AS $$
DECLARE
    emp_count INTEGER;
BEGIN
    SELECT COUNT(*) INTO emp_count
    FROM employees
    WHERE dept_id = dept_id_param;
    
    RETURN emp_count;
END;
$$ LANGUAGE plpgsql;

-- Usage:
SELECT dept_name, get_employee_count(dept_id) as employee_count
FROM departments;

-- Procedure to give salary raise
CREATE OR REPLACE PROCEDURE give_raise(
    emp_id_param INTEGER,
    raise_percent NUMERIC
)
LANGUAGE plpgsql
AS $$
BEGIN
    UPDATE employees
    SET salary = salary * (1 + raise_percent / 100)
    WHERE emp_id = emp_id_param;
    
    COMMIT;
END;
$$;

-- Usage:
CALL give_raise(1, 5);  -- Give 5% raise to employee with ID 1

-- Trigger to log salary changes
CREATE TABLE salary_log (
    log_id SERIAL PRIMARY KEY,
    emp_id INTEGER,
    old_salary NUMERIC(10, 2),
    new_salary NUMERIC(10, 2),
    change_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE OR REPLACE FUNCTION log_salary_changes()
RETURNS TRIGGER AS $$
BEGIN
    IF NEW.salary <> OLD.salary THEN
        INSERT INTO salary_log (emp_id, old_salary, new_salary)
        VALUES (NEW.emp_id, OLD.salary, NEW.salary);
    END IF;
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER salary_change_trigger
AFTER UPDATE OF salary ON employees
FOR EACH ROW
EXECUTE FUNCTION log_salary_changes();

-- Test the trigger
UPDATE employees SET salary = 62000 WHERE emp_id = 1;

-- View logged changes
SELECT * FROM salary_log;
```

This example includes:
1. Creating tables and inserting sample data
2. A function to get employee count by department
3. A procedure to give a salary raise
4. A trigger to log salary changes

You can practice by:
1. Querying the data using the function
2. Giving raises using the procedure
3. Updating salaries and checking the salary_log table to see the trigger in action

Feel free to modify these examples or create your own functions, procedures, and triggers to further practice PL/pgSQL!
