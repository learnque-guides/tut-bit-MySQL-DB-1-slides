# Working with characters

* For string concatenation, T-SQL provides the plus-sign (+) operator and the *CONCAT* function. 
* For other operations on character strings, T-SQL provides several functions, including *SUBSTRING, LEFT, RIGHT, LEN, DATALENGTH, CHARINDEX, PATINDEX, REPLACE, REPLICATE, STUFF, UPPER, LOWER, RTRIM, LTRIM, FORMAT, COMPRESS, DECOMPRESS, and STRING_SPLIT*.

```sql
SELECT empid, firstname + N' ' + lastname AS fullname
FROM HR.Employees
GO

SELECT custid, country, region, city,
  country + N',' + region + N',' + city AS location
FROM Sales.Customers
GO

SELECT custid, country, region, city,
  country + COALESCE( N',' + region, N'') + N',' + city AS location
FROM Sales.Customers
GO

SELECT custid, country, region, city,
  CONCAT(country, N',' + region, N',' + city) AS location
FROM Sales.Customers
GO -- CONCAT also removes NULL and replace with empty char
```

SUBSTRING(string, start, length)

```sql
SELECT SUBSTRING('abcde', 1, 3)
GO
```

LEFT(string, n), RIGHT(string, n)

```sql
SELECT RIGHT('abcde', 3)
GO
```

LEN(string)

```sql
SELECT LEN(N'abcde');
SELECT DATALENGTH(N'abcde');
```

CHARINDEX(substring, string[, start_pos])

```sql
SELECT CHARINDEX(' ','Itzik Ben-Gan');
```

PATINDEX(pattern, string)

```sql
SELECT PATINDEX('%[0-9]%', 'abcd123efgh');
```

REPLACE(string, substring1, substring2)

```sql
SELECT REPLACE('1-a 2-b', '-', ':');
```

REPLICATE(string, n)

```sql
SELECT REPLICATE('abc', 3);
```

STUFF(string, pos, delete_length, insert_string)

```sql
SELECT STUFF('xyz', 2, 1, 'abc'); -- xabcz
```

UPPER(string), LOWER(string)

```sql
SELECT UPPER('Itzik Ben-Gan');
SELECT LOWER('Itzik Ben-Gan');
```

RTRIM(string), LTRIM(string)

```sql
SELECT RTRIM(LTRIM('   abc   '));
```

FORMAT(input , format_string, culture)

[ http://go.microsoft.com/fwlink/?LinkId=211776](http://go.microsoft.com/fwlink/?LinkId=211776)

```sql
SELECT FORMAT(1759, '000000000');
```

Wildcarts

* The % wildcart - LIKE 'somestring%'
* The _ (underscore) wildcard

```sql
SELECT empid, lastname
FROM HR.Employees
WHERE lastname LIKE N'_e%';
```

* The [<list of characters>] wildcard

```sql
SELECT empid, lastname
FROM HR.Employees
WHERE lastname LIKE N'[ABC]%';
```

* The [<character>-<character>] wildcard

```sql
SELECT empid, lastname
FROM HR.Employees
WHERE lastname LIKE N'[A-E]%';
```

* The [^<character list or range>] wildcard (^ not in char list)

```sql
SELECT empid, lastname
FROM HR.Employees
WHERE lastname LIKE N'[^A-E]%';
```

* The ESCAPE character

If you want to search for a character that is also used as a wildcard (such as %, _, [, or ]), you can use an escape character.

*col1 LIKE ‘%!_%’ ESCAPE ‘!’* or LIKE ‘%[_]%’. [] lets to replace ESCAPE

