**Using WHERE class for many conditions**
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

### Operators
---
**NULL and ISNULL**
In SQL, **NULL** represents a missing or unknown value. We can check for NULL values using the expression **IS NULL**. For example, to count the number of missing values in a table:
```SQL
SELECT count(*)
FROM table_name
WHERE column_name IS NULL;
```

Most of the time, we will look for data which has no missing values. For that, we will need to filter the null values. The operator **IS NOT NULL** is used to return Non-missing data. For example:
```SQL
SELECT count(*)
FROM table_name
WHERE column_name IS NOT NULL;
```

**LIKE and NOT LIKE**
Normally, the **WHERE** clause can be used to filter text data. However, till this moment we have only been able to filter by specifying the exact text we want to reitreive. In the real world, often we will want to search for a pattern rather than a specific text string.

In SQL, the **LIKE** operator can be used in a WHERE clause to search for a pattern in a column. To accomplish this, we use something called a wildcard as a placeholder for some other values. There are two wildcards we can use with LIKE:

- The **%** wildcard will match zero, one, or many characters in text. For example, the following query matches companies like 'Data', 'DataC' 'DataCamp', 'DataMind', and so on:
```SQL
SELECT name
FROM companies
WHERE name LIKE 'Data%';
```

- The **_** wildcard will match a single character. For example, the following query matches companies like 'DataCamp', 'DataComp', and so on:
```SQL
SELECT name
FROM companies
WHERE name like 'DataC_mp';
```
We can also use the **NOT LIKE** operator to find records that don't match the pattern we specify.

---

### ORDER BY 

The ORDER BY keyword is used to sort results in ascending or descending order according to the values of one or more columns. By default, the ORDER BY keyword will sort the column in ascending order. However, to sort the column in descending order, we need to specify **DESC** command.

For example:
```sql
SELECT column_name
FROM table
ORDER BY column_02 DESC;
```

### GROUP BY
Often, we will need to aggregate results. For example: we might want to count the number of male and female employees in a company.
```sql
SELECT sex, count(*)
FROM table
GROUP BY sex;
```
Output:
| **sex** | **count** |
|:-------:|:---------:|
|male|19|
|female|12|


### HAVING
In SQL, aggregate functions can't be used in **WHERE** clauses. For example, the following query is invalid:

```sql
SELECT release_year
FROM films
GROUP BY release_year
WHERE COUNT(title) > 10;
```

This means that if we want to filter based on the result of an aggregate function, we need another way! That's where the **HAVING** clause comes in. For example:

```sql
SELECT release_year
FROM films
GROUP BY release_year
HAVING COUNT(title) > 10;
```

**INNER JOIN**

The INNER JOIN keyword selects all rows from the tables as long as there is a match between the columns. If there are records in one table that do not have matches in the other table, these orders will not be shown.

Example:
```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

### Joining Multiple Tables
```sql
SELECT *
FROM left_table
  INNER JOIN right_table
    ON left_table.id = right_table.id
  INNER JOIN another_table
    ON left_table.id = another_table.id;
```

### INNER JOIN via using
When the joining tables have the common column upon which these tables are being joined, we can use the **USING** command instead of **ON**.
```sql
SELECT lt.column_1, rt.column_2
FROM left_table AS lt
  INNER JOIN right_table AS rt
    USING (id);
```
Since the **id** column exists in both the tables.

### Self-ish Joins
Joins table with itself.






















