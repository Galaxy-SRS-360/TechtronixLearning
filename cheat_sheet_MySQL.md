# A handy cheat sheet for MySQL, covering common commands and operations:

### MySQL Cheat Sheet

#### Connecting to MySQL
```sh
# Connect to MySQL server
mysql -u username -p
```

#### Database Operations
```sql
-- List all databases
SHOW DATABASES;

-- Create a new database
CREATE DATABASE dbname;

-- Select a database
USE dbname;

-- Drop a database
DROP DATABASE dbname;
```

#### Table Operations
```sql
-- Show all tables in the selected database
SHOW TABLES;

-- Create a new table
CREATE TABLE tablename (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
);

-- Describe table structure
DESCRIBE tablename;

-- Drop a table
DROP TABLE tablename;

-- Alter a table (e.g., add a column)
ALTER TABLE tablename ADD columnname datatype;

-- Rename a table
RENAME TABLE oldname TO newname;
```

#### Data Manipulation
```sql
-- Insert data into a table
INSERT INTO tablename (column1, column2, ...) VALUES (value1, value2, ...);

-- Select data from a table
SELECT column1, column2 FROM tablename WHERE condition;

-- Update data in a table
UPDATE tablename SET column1 = value1, column2 = value2 WHERE condition;

-- Delete data from a table
DELETE FROM tablename WHERE condition;
```

#### Query Examples
```sql
-- Select all columns from a table
SELECT * FROM tablename;

-- Select specific columns with a condition
SELECT column1, column2 FROM tablename WHERE column3 = value;

-- Order results
SELECT * FROM tablename ORDER BY column1 ASC;
SELECT * FROM tablename ORDER BY column1 DESC;

-- Limit results
SELECT * FROM tablename LIMIT 10;

-- Count rows
SELECT COUNT(*) FROM tablename;

-- Group by a column
SELECT column1, COUNT(*) FROM tablename GROUP BY column1;

-- Use aliases
SELECT column1 AS alias1, column2 AS alias2 FROM tablename;
```

#### Functions
```sql
-- Aggregate functions
SELECT COUNT(column) FROM tablename;
SELECT AVG(column) FROM tablename;
SELECT SUM(column) FROM tablename;
SELECT MAX(column) FROM tablename;
SELECT MIN(column) FROM tablename;

-- String functions
SELECT CONCAT(string1, string2);
SELECT LENGTH(string);
SELECT UPPER(string);
SELECT LOWER(string);

-- Date functions
SELECT CURDATE();
SELECT CURTIME();
SELECT NOW();
SELECT DATE(column);
SELECT YEAR(column);
SELECT MONTH(column);
SELECT DAY(column);
```

#### Indexes
```sql
-- Create an index
CREATE INDEX indexname ON tablename (columnname);

-- Drop an index
DROP INDEX indexname ON tablename;

-- Show indexes
SHOW INDEX FROM tablename;
```

#### User Management
```sql
-- Create a new user
CREATE USER 'username'@'host' IDENTIFIED BY 'password';

-- Grant privileges
GRANT ALL PRIVILEGES ON dbname.* TO 'username'@'host';
GRANT SELECT, INSERT, UPDATE ON dbname.* TO 'username'@'host';

-- Show grants
SHOW GRANTS FOR 'username'@'host';

-- Revoke privileges
REVOKE ALL PRIVILEGES ON dbname.* FROM 'username'@'host';

-- Drop a user
DROP USER 'username'@'host';
```

#### Backup and Restore
```sh
# Backup database
mysqldump -u username -p dbname > backup.sql

# Restore database
mysql -u username -p dbname < backup.sql
```

This cheat sheet covers many of the common tasks you'll perform in MySQL. Keep this as a quick reference guide for working with MySQL databases.
