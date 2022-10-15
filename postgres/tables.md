# Postgres tables operations


### Create table
```
CREATE TABLE notes (
        id serial,
        title label,
        remarks text
);
```
Reference: https://www.postgresql.org/docs/current/sql-createtable.html 


### Insert data
```
INSERT INTO notes (title, remarks) VALUES ('Finish task1', 'Some more details');

Reference: https://www.postgresql.org/docs/current/sql-insert.html
