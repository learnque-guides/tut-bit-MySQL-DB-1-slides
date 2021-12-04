# DQL - Select statement

The purpose of a SELECT statement is to query tables, apply some logical manipulation, and return a result.

The SELECT statement allows you to read data from one or more tables:
* Firstly, you specify a list of columns or expressions that you want to show in the result.
* Then you specify the table that you want to select from.

```sql
SELECT select_list
FROM table_name
[WHERE condition]; -- predicate statement
```
---

```sql
SELECT * FROM table_name;
```

---

```sql
SELECT col1, col2 FROM table_name;
```

The simplest query examples:

```sql
USE lessons;

SELECT * FROM Sales.Orders;
```

Note:

Use of an asterisk is considered a bad programming practice in most cases. It is recommended that you explicitly list all attributes you need. Unlike with the relational model, SQL keeps ordinal positions for columns based on the order in which you specified them in the *CREATE TABLE* statement. By specifying <i>SELECT *</i>, you’re guaranteed to get the columns ordered in the output based on their ordinal positions. Client applications can refer to columns in the result by their ordinal positions (a bad practice in its own right) instead of by name. Then any schema changes applied to the table—such as adding or removing columns, rearranging their order, and so on—might result in failures in the client application or, even worse, in application bugs that will go unnoticed. By explicitly specifying the attributes you need, you always get the right ones, as long as the columns exist in the table. If a column referenced by the query was dropped from the table, you get an error and can fix your code accordingly.
