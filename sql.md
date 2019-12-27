# SQL - Structured Query Language

## Comments
`--comments` or `/* comments */`

## Datatypes
* BOOLEAN
* INT
* FLOAT
* VARCHAR(255)
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
* =, >, <, >=, <=, <>
* BETWEEN, LIKE, IN

`LIKE` - pattern matching
```sql
SELECT column(s) FROM table_name WHERE columnN LIKE pattern;
```
###### Wildcard characters:
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

`BETWEEN` - between values
`NOT BETWEEN`
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

`LENGTH` - length of the element
`ROUND` - round integers to the nearest decimal

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
