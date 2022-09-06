This course is about:
1. How to explore a SQL database?
2. Summarize different types of data, and deal with messy data.
3. Deal with messy data

In this course, we are going to use PostgreSQL.

So, what is a Database Client?
A **database client** is a program used to connect to, and work with, a database.

Entity Relationship Diagram
Structure of the database that shows the tables, their columns, and the relationships between them.

**Few things to remember:**
- NULL indicates missing data in a database.
- To check which values are NULL, use "is NULL" or "is not NULL"
- The count function with a star counts the number of rows.
- If you instead supply a column name to the count function, it counts the number of non-NULL observations in the column. 
This is equal to the total number of rows, minus the number of NULL values.
- If you count the distinct values of a column, you'll get the number of different non-NULL values in the column.
- But if you select those distinct values directly, NULL will be included as a value if it exists in the column, even though it isn't counted by the count function.
