## ```LIMIT```
- returns a subset of rows
- since the order of rows is unpredictable, it is good practice to use it with an ```ORDER BY``` clause

Return ```n``` number of rows:
```
SELECT
  *
FROM
  myTableName
LIMIT n;
```

When ```n``` is zero or ```NULL```, has the same effect as omitting the ```LIMIT``` clause.

### ```LIMIT n OFFSET m ```
- skip ```m``` number of rows before returning ```n``` number of rows.

```
SELECT
  *
FROM
  myTableName
LIMIT n OFFSET m;
```
- using large offsets is not efficient -> since the database server still needs to calculate the m number of rows and skip them
