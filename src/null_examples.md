# NULL examples

```sql
SELECT custid, country, region, city
FROM Sales.Customers
WHERE region = NULL -- will return empty
GO
```

```sql
SELECT custid, country, region, city
FROM Sales.Customers
WHERE region IS NULL -- will return 60 rows
GO
```

If you want to get region that are not null

```sql
SELECT custid, country, region, city
FROM Sales.Customers
WHERE region IS NOT NULL -- will return 31 rows
GO
```
