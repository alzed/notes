# SQL

Structured Query Language

## Comments

`--comments` or `/* comments */`

## Datatypes

* BOOLEAN
* INT
* FLOAT
* VARCHAR\(255\)
* TEXT - string of unlimited length
* DATE
* DATETIME
* TIME
* BLOB

## Data Manipulation clauses

* SELECT - extracts data from a database

  ```sql
  SELECT column(s) FROM table_name;
  ```

* INSERT INTO - inserts new data into a database

  ```sql
  INSERT INTO table_name (column(s)) VALUES (value(s))
  ```

* UPDATE - updates data in a database

  ```sql
  UPDATE table_name
  SET column1 = value1, column2 = value2, WHERE condition;
  ```

* DELETE - deletes data from a database

  ```sql
  DELETE FROM table_name WHERE condition;
  ```

## Conditional clause

`WHERE` - conditional

## Operators

* AND, OR, NOT - logical operations
* =, &gt;, &lt;, &gt;=, &lt;=, &lt;&gt;
* BETWEEN, LIKE, IN

`LIKE` - pattern matching

```sql
SELECT column(s) FROM table_name WHERE columnN LIKE pattern;
```

### Wildcard characters:

* `%` - 0 or more
* `_` - 1
* `[]` - exact characters
* `^` - not
* `-` - range

`IN` - contains  
`NOT IN` - not contains

```sql
SELECT column_name(s) FROM table_name WHERE column_name IN (value1, value2, ...);
SELECT column_name(s) FROM table_name WHERE column_name IN (SELECT STATEMENT);
```

`BETWEEN` - between values `NOT BETWEEN`

```sql
SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2;
```

## Other clauses

`*` - all columns

`DISTINCT` - unique elements

```sql
SELECT DISTINCT column(s), FROM table_name;
```

`AS` - alias

```sql
SELECT column_name AS alias_name FROM table_name;
SELECT column_name(s) FROM table_name AS alias_name;
```

`TOP` = `LIMIT` = `ROWNUM`

```sql
SELECT TOP number|percent column_name(s) FROM table_name WHERE condition;
SELECT column_name(s) FROM table_name WHERE condition LIMIT number;
SELECT column_name(s) FROM table_name WHERE ROWNUM <= number;
```

`COUNT` - count of elements

```sql
SELECT COUNT(column_name) FROM table_name WHERE condition;
```

`AVG` - average of elements

```sql
SELECT AVG(column_name) FROM table_name WHERE condition;
```

`SUM` - sum of elements

```sql
SELECT SUM(column_name) FROM table_name WHERE condition;
```

`LENGTH` - length of the element `ROUND` - round integers to the nearest decimal

`MIN` and `MAX`

```sql
SELECT MIN(column_name) FROM table_name WHERE condition;
SELECT MAX(column_name) FROM table_name WHERE condition;
```

`ORDER BY ... ASC|DESC`

`IS NULL` - testing null values  
`IS NOT NULL` - testing not null

`UNION` - union distinct values

```sql
SELECT column_name(s) FROM table1 UNION SELECT column_name(s) FROM table2;
```

`UNION ALL` - union duplicate values

```sql
SELECT column_name(s) FROM table1 UNION ALL SELECT column_name(s) FROM table2;
```

`GROUP_BY`

```sql
SELECT column(s) FROM table_name WHERE condition GROUP BY column(s) ORDER BY column(s);
```

`HAVING` - where with aggregate functions

```sql
SELECT column(s) FROM table WHERE condition GROUP BY column(s) HAVING condition ORDER BY column(s);
```

`EXISTS` - returns true if subquery returns one or more records

```sql
SELECT column(s) FROM table_name WHERE EXISTS (SELECT column FROM table WHERE condition);
```

`ANY` - returns true if any of the subquery values meet the condition

```sql
SELECT column(s) FROM table WHERE column operator ANY (SELECT column FROM table WHERE condition);
```

`ALL` - returns true if all of the subquery values meet the condition

```sql
SELECT column(s) FROM table WHERE column operator ALL (SELECT column FROM table WHERE condition);
```

**Switch case**

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

## Functions

`COALESCE` in psql or `IFNULL` in sql

* returns first non null value from arguments  
* used to replace default value for null values

  ```sql
  SELECT COALESCE (argument1, argument2, ...)
  SELECT IFNULL(argument1, argument2, ...)
  ```

## Joins

* JOIN - \(INNER\) JOIN

  ```sql
  SELECT column(s) FROM table1 INNER JOIN table2 ON table1.column = table2.column;
  ```

* LEFT JOIN

  ```sql
  SELECT column(s) FROM table1 LEFT JOIN table2 ON table1.column = table2.column;
  SELECT column(s) FROM table1 LEFT OUTER JOIN table2 ON table1.column = table2.column;
  ```

* RIGHT JOIN

  ```sql
  SELECT column(s) FROM table1 RIGHT JOIN table2 ON table1.column = table2.column;
  SELECT column(s) FROM table1 RIGHT OUTER JOIN table2 ON table1.column = table2.column;
  ```

* FULL JOIN

  ```sql
  SELECT column(s) FROM table1 FULL OUTER JOIN table2 ON table1.column = table2.column;
  ```

* CROSS JOIN

  ```sql
  SELECT column(s) FROM table1 CROSS JOIN table2 ON table1.column = table2.column;
  ```

* Self join

  ```sql
  SELECT column(s) FROM table1 T1, table1 T2 WHERE condition;
  ```

## Other select clauses

`SELECT INTO` - copies data from one table into a new table

```sql
SELECT column(s) INTO newtable [IN externaldb] FROM oldtable WHERE condition;
```

`INSERT INTO SELECT` - copies data from one table into a another table

```sql
INSERT INTO table2 SELECT * FROM table1 WHERE condition;
```

## Procedure

```sql
CREATE PROCEDURE procedure_name AS sql_statement GO;
EXEC procedure_name;
```

## Database Schema Manipulations

`CREATE TABLE` - creates a new table

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    columnN datatype,
   ...
);
```

Create table from existing table

```sql
CREATE TABLE new_table_name AS
    SELECT column1, column2,...
    FROM existing_table_name
    WHERE ...;
```

`ALTER TABLE` - modifies a table

```sql
ALTER TABLE table_name ADD column_name datatype;
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name MODIFY COLUMN column_name datatype;
```

`DROP TABLE` - deletes a table

```sql
DROP TABLE table_name;
DROP DATABASE - drops existing database
DROP DATABASE databasename
```

## SQLDB:

`CREATE DATABASE` - creates a new database

```sql
CREATE DATABASE databasename;
```

`BACKUP DATABASE` - creates full backup of existing database

```sql
BACKUP DATABASE databasename TO DISK = 'filepath';
```

`differential` - backs up parts of database changed since last backup

```sql
BACKUP DATABASE databasename TO DISK = 'filepath' WITH DIFFERENTIAL;
```

`ALTER DATABASE` - modifies a database

```sql
ALTER TABLE table_name ALTER COLUMN column_name datatype;
```

`TRUNCATE` - delete data inside table, not table

```sql
TRUNCATE TABLE table_name;
```

`CREATE INDEX` - creates an index \(search key\)

```sql
DROP INDEX - deletes an index
```

## Constraints

`NOT NULL` - Ensures that a column cannot have a NULL value  
`UNIQUE` - Ensures that all values in a column are different  
`PRIMARY KEY` - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table

`FOREIGN KEY` - Uniquely identifies a row/record in another table  
`FOREIGN KEY (column) REFERENCES table(column)`

`CHECK` - Ensures that all values in a column satisfies a specific condition  
`DEFAULT` - Sets a default value for a column when no value is specified  
`INDEX` - Used to create and retrieve data from the database very quickly

**Examples**

```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ...
);

ALTER TABLE table_name MODIFY COLUMN column_name datatype constraint;

CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    CONSTRAINT column constraint (column1, column2, ...),
    ...
);
```

### References

1. [https://sqlbolt.com/](https://sqlbolt.com/)
2. [https://sqlzoo.net/](https://sqlzoo.net/)

