# SQL parts

* SQL has several categories of statements, including:
    * Data Query language (DQL).
    * Data Definition Language (DDL). 
    * Data Manipulation Language (DML).
    * Data Control Language (DCL).

* DQL - data query language. Helps users retrieve information from the database.
* DDL deals with object definitions and includes statements such as CREATE, ALTER, and DROP. 
* DML allows you to query and modify data and includes statements such as SELECT, INSERT, UPDATE, DELETE, TRUNCATE, and MERGE. It’s a common misunderstanding that DML includes only data-modification statements, but as I mentioned, it also includes SELECT. Another common misunderstanding is that TRUNCATE is a DDL statement, but in fact it is a DML statement. 
* DCL deals with permissions and includes statements such as GRANT and REVOKE.

*Note: SELECT statement is strictly speaking an example of DQL. When adding FROM or WHERE data manipulators to the SELECT statement the statement is then considered part of the DML.*
