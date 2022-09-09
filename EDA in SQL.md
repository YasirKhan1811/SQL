This course is about:
1. How to explore a SQL database?
2. Summarize different types of data
3. Deal with messy data

In this course, we are going to use PostgreSQL.

So, what is a Database Client?
A **database client** is a program used to connect to, and work with, a database.

Entity Relationship Diagram
Structure of the database that shows the tables, their columns, and the relationships between them.

![image](https://user-images.githubusercontent.com/96954071/189028126-2a54e764-8dc0-4739-97c3-1c03749c3614.png)

**Few things to remember:**
- NULL indicates missing data in a database.
- To check which values are NULL, use "is NULL" or "is not NULL"
- The count function with a star counts the number of rows.
- If you instead supply a column name to the count function, it counts the number of non-NULL observations in the column. 
This is equal to the total number of rows, minus the number of NULL values.
- If you count the distinct values of a column, you'll get the number of different non-NULL values in the column.
- But if you select those distinct values directly, NULL will be included as a value if it exists in the column, even though it isn't counted by the count function.

**Counting the no. of rows and columns in a database tables:**

```
To know the number of columns in a table:
SELECT *
FROM tablename;

To know the number of rows in a table:
SELECT count(*)
FROM tablename;
```

Knowing how much data you have is a first step in exploratory data analysis.

**Count missing values**
To count the number of missing values in a column:
```
SELECT count(*) - count(column_name) AS missing
FROM table_name;
```

Note: When you supply a column name as the input to count(), it returns the number of non-NULL values.


### Join Tables
- Part of exploring a database is figuring out how tables relate to each other. To join the tables, we need to find a column that they have in common where the values are consistent across the tables
- Remember: just because two tables have a column with the same name, it doesn't mean those columns necessarily contain compatible data
- If we find more than one pair of columns with similar data, we may need to try joining with each pair one-by-one to see if number of results are same


## The Keys to the Database
The second stage of exploring a database is understanding the formal relationships, or links, between tables.








