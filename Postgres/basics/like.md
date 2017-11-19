### ```LIKE``` or ```NOT LIKE```
- returns rows where the values match a pattern

```string LIKE pattern```

```string NOT LIKE pattern```

Two wildcard characters can be used:

```%```: matching any sequence of characters
```_```: matching any single character

```
SELECT
  name,
  age
FROM
  students
where
  name LIKE 'Em%';
```
