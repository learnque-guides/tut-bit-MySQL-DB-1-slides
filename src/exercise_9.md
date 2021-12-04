# Exercise 9

Write a query against the *Sales.Customers* table that returns for each customer the customer ID and region. Sort the rows in the output by region, having NULLs sort last (after non-NULL values). Note that the default sort behavior for NULLs in T-SQL is to sort first (before non-NULL values):

* Tables involved: *lessons* database and the *Sales.Customers* table
* Desired output (abbreviated):
```
custid      region
----------- ---------------
55          AK
10          BC
42          BC
45          CA
37          Co. Cork
33          DF
71          ID
38          Isle of Wight
46          Lara
78          MT
...
1           NULL
2           NULL
3           NULL
4           NULL
5           NULL
6           NULL
7           NULL
8           NULL
9           NULL
11          NULL
...

(91 row(s) affected)
```

Tip:

*By default, SQL Server sorts NULLs before non-NULL values. To get NULLs to sort last, you can use a CASE expression that returns 1 when the region column is NULL and 0 when it is not NULL. Specify this CASE expression as the first sort column and the region column as the second. This way, non-NULLs sort correctly among themselves first followed by NULLs.*