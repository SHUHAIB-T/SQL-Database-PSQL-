# Introduction

- `Databse:` 
    - The place we can store the related data and later retrieve the data is known as Database.
- `Database Management System DBMS`
    - Software that stores data in databases in an organized way to make it easier to create, retrieve, update etc
    - Examples: DBase, FoxPro, MySQL, Oracle, MangoDB, MariaDB, SQLite, Cassandra and many more
- `RDBMS` 
    - DBMS using Relational Data Models are known as RDBMS
    - Oracle, MS-SQL Server, DB2, MySQL, MS-ACCESS, PostgrSQL, etc. 
- `SQL`
    - It is the Query Language for Relational Data Bases.


# Concepts in SQL Data Base
****
- #### ACID PROPERTIES
    - `Atomicity` : ensure that the transaction are treated as single, indivisible and either fully completd or aborted.
    - `Consistency` : Guarantees that a transaction brings a database from one valid state to another.
    - `Isolation` : Ensure that the concurrent transaction do not interfere with each other. preserves the consistency of the database.
    - `Durability` : Once a transaction is committed, its changes are permanent and survive the system faiure.
- #### Normalization
    - process of organizing the data in the database to eliminate redundancy and improve data integrity.
    - 



***
## Postgres SQL

PostgreSQL is a powerful, open source object-relational database system with over 35 years of active development that has earned it a strong reputation for reliability, feature robustness, and performance.


```
CREATE DATABASE vehicles;
```

`\l` is for viewing all the databases, `\c` is to go to the database we created.
in sql every query will end with semicolon ';'.

```
\c vehicles;
```

```
CREATE TABLE cars;
```

```
INSERT INTO cars(brand VARCHAR(255), year INT , color VARCHAR(255) )
VALUES ('volvo',2013,'red');
```