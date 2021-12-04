# Exercise 5

To check the validity of the data, write a query against the *HR.Employees* table that returns employees with a last name that starts with a lowercase English letter in the range a through z.

Note: You need to specify `COLLATE Latin1_General_CS_AS` before `LIKE`. The collation of the sample database is case insensitive (Latin1_General_CI_AS)

* Tables involved: *lessons* database and the *HR.Employees* table
* Desired output is an empty set:

empid       lastname
----------- --------------------

(0 row(s) affected))