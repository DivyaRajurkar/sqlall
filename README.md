# SQL SELECT Statement - README

## Overview
The SQL **SELECT** statement is used to retrieve data from a database. It allows users to specify the columns they want to fetch and the table from which they want to fetch the data. This is one of the most fundamental and commonly used operations in SQL.

---

## Syntax
```sql
SELECT column1, column2, ...
FROM table_name;
```

### Components:
- **column1, column2, ...**: The fields (columns) you want to retrieve.
- **table_name**: The name of the table you want to query.

---

## Example Query
To fetch the `CustomerName` and `City` columns from the `Customers` table:
```sql
SELECT CustomerName, City
FROM Customers;
```

---

## Sample Data: Customers Table
Below is the sample data used in the examples:

| CustomerID | CustomerName                       | ContactName        | Address                | City       | PostalCode | Country   |
|------------|------------------------------------|--------------------|------------------------|------------|------------|-----------|
| 1          | Alfreds Futterkiste               | Maria Anders       | Obere Str. 57          | Berlin     | 12209      | Germany   |
| 2          | Ana Trujillo Emparedados y helados| Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico    |
| 3          | Antonio Moreno Taquería           | Antonio Moreno     | Mataderos 2312         | México D.F.| 05023      | Mexico    |
| 4          | Around the Horn                   | Thomas Hardy       | 120 Hanover Sq.        | London     | WA1 1DP    | UK        |
| 5          | Berglunds snabbköp                | Christina Berglund | Berguvsvägen 8         | Luleå      | S-958 22   | Sweden    |

---

## SQL Statements

### 1. Create Table
To create the `Customers` table:
```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    CustomerName VARCHAR(255),
    ContactName VARCHAR(255),
    Address VARCHAR(255),
    City VARCHAR(100),
    PostalCode VARCHAR(20),
    Country VARCHAR(100)
);
```

### 2. Insert Data
To populate the `Customers` table with the sample data:
```sql
INSERT INTO Customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES
(1, 'Alfreds Futterkiste', 'Maria Anders', 'Obere Str. 57', 'Berlin', '12209', 'Germany'),
(2, 'Ana Trujillo Emparedados y helados', 'Ana Trujillo', 'Avda. de la Constitución 2222', 'México D.F.', '05021', 'Mexico'),
(3, 'Antonio Moreno Taquería', 'Antonio Moreno', 'Mataderos 2312', 'México D.F.', '05023', 'Mexico'),
(4, 'Around the Horn', 'Thomas Hardy', '120 Hanover Sq.', 'London', 'WA1 1DP', 'UK'),
(5, 'Berglunds snabbköp', 'Christina Berglund', 'Berguvsvägen 8', 'Luleå', 'S-958 22', 'Sweden');
```

### 3. Query Data
To retrieve specific data from the `Customers` table:
```sql
SELECT CustomerName, City
FROM Customers;
```

---

## Summary
The **SELECT** statement is an essential SQL command for retrieving data from a database. By combining it with other SQL commands, you can perform powerful data manipulations and analyses.

For more advanced queries, consider exploring filtering (`WHERE`), sorting (`ORDER BY`), grouping (`GROUP BY`), and joining multiple tables (`JOIN`).
### **SQL SELECT DISTINCT Statement**

The `SELECT DISTINCT` statement in SQL is used to retrieve only unique (distinct) values from a column or combination of columns in a table. This is useful when a column contains duplicate values, and you need to eliminate redundancy in the results.

---

### **Key Features:**
1. **Purpose**: Returns only distinct values from the specified columns.
2. **Eliminates Duplicates**: Filters out repeated values in the result set.
3. **Applies to Columns**: Can be applied to one or multiple columns to fetch unique combinations of data.

---

### **Syntax:**
```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

---

### **Example:**

**Table**: *Customers*

| CustomerID | CustomerName                   | Country  |
|------------|--------------------------------|----------|
| 1          | Alfreds Futterkiste           | Germany  |
| 2          | Ana Trujillo Emparedados y Helados | Mexico |
| 3          | Antonio Moreno Taquería       | Mexico   |
| 4          | Around the Horn               | UK       |
| 5          | Berglunds snabbköp            | Sweden   |

- **Query Without DISTINCT**:
  ```sql
  SELECT Country FROM Customers;
  ```
  **Output**:  
  Germany, Mexico, Mexico, UK, Sweden  

- **Query With DISTINCT**:
  ```sql
  SELECT DISTINCT Country FROM Customers;
  ```
  **Output**:  
  Germany, Mexico, UK, Sweden  

---

### **Important Notes:**
- When using multiple columns with `DISTINCT`, it considers the combination of values in those columns:
  ```sql
  SELECT DISTINCT column1, column2 FROM table_name;
  ```
- Performance may be impacted for large datasets due to the need for comparison of all records.
- Always use `DISTINCT` judiciously to avoid unnecessary computational overhead. 

This feature is particularly useful in scenarios like filtering unique categories, countries, or any other non-repetitive data within a database.
