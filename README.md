# 
QL SELECT Statement: Explanation and Example
The SELECT statement is used to retrieve data from a database. You can specify the columns you want to retrieve and the table from which you want to fetch the data.

Syntax:
sql
Copy code
SELECT column1, column2, ...
FROM table_name;
column1, column2, ...: Names of the fields (columns) you want to retrieve.
table_name: The name of the table in the database.
Example Query:
The following query retrieves the CustomerName and City columns from the Customers table:

sql
Copy code
SELECT CustomerName, City 
FROM Customers;
