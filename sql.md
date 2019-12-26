# SQL

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
