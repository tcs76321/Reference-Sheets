# SQL, Structured Query Language

## Context: 

1 - SQL is used to create, read, update, and delete large amounts of structured data within realational database management systems.

2 - Utilizes english language keywords and a simple syntax system.

3 - A relational database is comprised of tables. Tables themselves have fields or columns which are different data types, such as numbers, strings and datetimes.

4 - Where as the columns of a table are the kinds of pieces of data the table will store, the rows or entries are actual pieces of said data. A 'Customer' table could have columns including a 'firstname' field of type VARCHAR(32), which would allow strings up to length 32.

5 - Every table has PRIMARY KEYs, which must be unique to that entry, aka row, across the table. Relations are defined by FOREIGN KEYs, which tie a secondary field/column of one table to the PRIMARY KEY of a second table. 

6 - For example, an Order table could have a FOREIGN KEY column relating to a Customer table's PRIMARY KEYs. Depending on how the foreign key relation is defined, deleting a Customer table row could automatically trigger the deletion of all relation Order rows as well.

## Basic Queries:

Retrieve the first_name and age column data points for all the rows in Customers.
```
SELECT first_name, age
FROM Customers;
```

TO BE CONTINUED
