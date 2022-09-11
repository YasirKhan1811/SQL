**INNER JOIN**

The INNER JOIN keyword selects all rows from the tables as long as there is a match between the columns. If there are records in one table that do not have matches in the other table, these orders will not be shown.

Example:
```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

Using WHERE class for many conditions:
```SQL
SELECT name
FROM kids
WHERE age = 2
OR age = 4
OR age = 6
OR age = 8
OR age = 10;
```

Use the **IN** operator instead
```SQL
SELECT name
FROM kids
WHERE age IN (2, 4, 6, 8, 10);
```
