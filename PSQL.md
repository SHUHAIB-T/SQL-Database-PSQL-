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
