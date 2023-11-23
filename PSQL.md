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

### Transaction
it is a group of operations or a set of statments that exicuted as a single work of unit.

- the whole transaction is treated as a single unit. so if there any errors occur during the transaction before commit it will all roll back. no changes will be committed. 

example for a transaction:
````
begin;
-- operation one 
update accounts
set balance = balance + 1000
where id = 1;

-- operation two
update accounts 
set balance = balance - 1000;
where id = 2;

commit;
end;
````
if there any error occur in during the transaction before commit like system will fail or power loss etc, the transaction will be aborted. we can create a failiure inside a transaction by using the word `rollback`.

### views

views are just virtual tables that can derived  form  underlaying base table or previously defined views.
 - limit and update options can be applied in views. 
 - 

### stored procedures

it is like user defined functions in sql. we create a procedure and compile it, whenever we want to use that we can use 'call procedure_name'.
- this will make our application faster because we can save the compailation time.
- code reusablity

### cursor

- cursor is used along with table containg large amount of data. when we use select property for a table containg large amount of data it will take some time to process or it will shows an error "Out of memory".
- cursor can only be declared inside transaction. 

cursor syntax:
````
DECLARE 
[cursor name] CURSOR FOR [query]
````

example usage:
products is a table containing 77 rows. 
```
BEGIN;

DECLARE 
my_cursor CURSOR FOR
SELECT * FROM products;

 - FETCH 10 FROM my_cursor;
 - FETCH PRIOR FROM my_cursor; 

 COMMIT;
```
### Triggers

it is like a user defined function that triggers automatically when an enveny is happened. event can be anything like CREATE, DELETE, UPDATE etc. 