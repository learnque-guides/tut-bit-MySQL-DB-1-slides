# The *OFFSET functions

SWITCHOFFSET(datetimeoffset_value, UTC_offset)

```sql
SELECT SWITCHOFFSET(SYSDATETIMEOFFSET(), '-05:00');
```

TODATETIMEOFFSET(local_date_and_time_value, UTC_offset)

This function is different from *SWITCHOFFSET* in that its first input is a local date and time value without an offset component. This function simply merges the input date and time value with the specified offset to create a new datetimeoffset value.

We can specify time zone as well:

```sql
SELECT
  CAST('20160212 12:00:00.0000000' AS DATETIME2)
    AT TIME ZONE 'Pacific Standard Time' AS val1,
  CAST('20160812 12:00:00.0000000' AS DATETIME2)
    AT TIME ZONE 'Pacific Standard Time' AS val2;
```

## The DATEADD function

DATEADD(part, n, dt_val)

```sql
SELECT DATEADD(year, 1, '20160212');
```

## The DATEDIFF and DATEDIFF_BIG Functions

```sql
SELECT DATEDIFF(day, '20150212', '20160212');
SELECT DATEDIFF_BIG(millisecond, '00010101', '20160212');
```

## The DATEPART function

DATEPART(part, dt_val)

```sql
SELECT DATEPART(month, '20160212');
```

## The YEAR, MONTH, and DAY functions

YEAR(dt_val)
MONTH(dt_val)
DAY(dt_val)

```sql
SELECT
  DAY('20160212') AS theday,
  MONTH('20160212') AS themonth,
  YEAR('20160212') AS theyear;
```

## The DATENAME function

DATENAME(dt_val, part)

```sql
SELECT DATENAME(month, '20160212');
```

## The ISDATE function

ISDATE(string)

```sql
SELECT ISDATE('20160212');
SELECT ISDATE('20160230');
```

and so on:

```sql
SELECT
  DATEFROMPARTS(2016, 02, 12),
  DATETIME2FROMPARTS(2016, 02, 12, 13, 30, 5, 1, 7),
  DATETIMEFROMPARTS(2016, 02, 12, 13, 30, 5, 997),
  DATETIMEOFFSETFROMPARTS(2016, 02, 12, 13, 30, 5, 1, -8, 0, 7),
  SMALLDATETIMEFROMPARTS(2016, 02, 12, 13, 30),
  TIMEFROMPARTS(13, 30, 5, 1, 7);
```

## The EOMONTH function

EOMONTH(input [, months_to_add])

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
WHERE orderdate = EOMONTH(orderdate);
```