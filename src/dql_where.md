# DQL - Where clause

* The WHERE clause allows you to specify a search condition for the rows returned by a query.
* By specifying a condition, the SELECT instruction will no longer return all of the results but only those that match the specified condition.
* The search condition is a combination of one or more predicates using the logical operator AND, OR and NOT.

```sql
SELECT select_list
FROM table_name
WHERE condition; -- predicate
```

The WHERE clause allows you to specify a number of comparison operators:

* a=b
* a>b, a>b, a<=b, a>=b
* a IN (value1, value2, value3)
* a IS NULL, a IS NOT NULL
* a!=b
* a BETWEEN b AND c
* a LIKE b

The WHERE clause allows you to specify logical operators that can be used to combine multiple comparison operators:
* AND 
* OR 
* NOT

*Only rows for which the logical expression evaluates to TRUE are returned by the WHERE phase. Always keep in mind that T-SQL uses three-valued predicate logic, where logical expressions can evaluate to TRUE, FALSE, or UNKNOWN.*

Examples :)