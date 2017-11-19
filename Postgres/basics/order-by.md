### ```ORDER BY```

- when you query data from PostgreSQL, by default it order them by the date of their creation
- with ```ORDER BY``` you can return data in ascending or descending order based on a selection criteria


```
SELECT
  columnA,
  columnB
FROM
  myTableName
ORDER BY
  columnA ASC,
  columnB DESC;
```

NOTE: in SQL you can ```ORDER BY``` based on the columns that appear in ```SELECT```, in PotgreSQL you are allowed to sort base don columns that don't appear in the selection list.
