# Exercise 2

Write a query against the Sales.Orders table that returns orders placed on the last day of the month:

* Tables involved: *lessons* database and the *Sales.Orders table*
* Desired output (abbreviated):

orderid     orderdate  custid      empid
----------- ---------- ----------- -----------
10269       2014-07-31 89          5
10317       2014-09-30 48          6
10343       2014-10-31 44          4
10399       2014-12-31 83          8
10432       2015-01-31 75          3
10460       2015-02-28 24          8
10461       2015-02-28 46          1
10490       2015-03-31 35          7
10491       2015-03-31 28          8
10522       2015-04-30 44          4
...

(26 row(s) affected)