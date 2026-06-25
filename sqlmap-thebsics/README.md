# SQLMap: The Basics 

## Task 01: Introduction

-  The databases are managed by Database Management Systems (DBMS), such as MySQL, PostgreSQL, SQLite, or Microsoft SQL Server.
-  These systems understand the Structured Query Language (SQL).

### Question

Which language builds the interaction between a website and its database?

### Answer

SQL

## Task 02: SQL Injection Vulnerability

- Taking an example of login page, once we enter username and password, the website will receive it, make an SQL query with credentials, and send it to the database.
- Username: John
  Password: Un@detectable444
- SELECT * FROM users WHERE username = 'John' AND password = 'Un@detectable444';
- Attackers can manipulate the input and write SQL queries that would get executed in the database and perform the attacker’s desired actions.
- Username: John
  Password: abc' OR 1=1;-- -
- SELECT * FROM users WHERE username = 'John' AND password = 'abc' OR 1=1;-- -';
### Question

Which boolean operator checks if at least one side of the operator is true for the condition to be true?

### Answer

OR

### Question

Is 1=1 in an SQL query always true? (YEA/NAY)

### Answer

YEA




