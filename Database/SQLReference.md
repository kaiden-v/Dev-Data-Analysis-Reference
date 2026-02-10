# SQL reference 

## Introduction 
SQL (Structured Query Language) is a standard language used to manage and manipulate relational databases. It allows you to query data, insert, update, and delete records, as well as define and manage database structures. SQL is widely used in database management systems like MySQL, PostgreSQL, SQLite, and SQL Server. In a relational database, data is organised into tables. Columns represent attributes or fields of the data (such as name, age, or salary), while rows represent individual records or instances of the data, with each row containing a value for each column

This document is intended as a practical reference, focusing on the SQL features you will commonly use when:
- querying and analysing data
- maintaining databases
- building reports and dashboards
- performing data transformations

It should be noted that each relational database system may have its own syntax, but most share the same basic structure as shown here. For additional or system-specific syntax, it is best to refer to the official documentation of the database you are using.

### Guide Sections 

---

## Selecting Data
The `SELECT` statement is the foundation of querying in SQL. It retrieves data from one or more tables. All rows and column data can be retrieved through the statement
```sql 
SELECT * 
FROM <table>;
```
Additionally, specific columns can be selected by specifying each name as such
```sql
SELECT <column1>, <column2>, ...
FROM <table>;
```
