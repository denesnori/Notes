### ``` SELECT DISTINCT```

- the ```DISTINCT``` clause is used to remove duplicate rows
- it can be used on any number of columns
- if you use it on more than one column, it removes the duplicates based on the combination of values in the specified columns

```
SELECT
  DISTINCT columnA,
  columnB,
  columnC
FROM
  myTableName;
```

```DISTINCT ON (expression)```
- keep the '1st' row of duplicates -> the order of rows returned form a ```SELECT``` is unpredictable -> the first row is unpredictable too
- suggestion: always use ```ORDER BY``` which makes it predictable
- the ```DISTINCT ON``` expression must match the leftmost expression in the ```ORDER BY``` clause.

```
SELECT
  DISTINCT ON
  (columnA),
  columnB,
  columnC
FROM
  myTableName
ODER BY
  columnA,
  columnB;
```
