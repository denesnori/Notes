### Select

Clauses that can appear in ```SELECT``` statements:
- ```DISTINCT``` -> to select distinct rows
- ```WHERE``` to filter rows
- ```ORDER BY``` -> to sort rows
- ```BETWEEN```, ```IN```, ```LIKE```
- ```GROUP BY``` -> to group similar rows
- ```HAVING``` -> to apply conditions
- ```INNER JOIN```, ```LEFT JOIN```, ```FULL OUTER JOIN```, ```CROSS JOIN``` -> to join tables


**SELECT** statements retrieve data from a single table.

Syntax:
- name the columns you want to retrieve data from or use the asterisk ```*``` operator to get all the columns.

```
SELECT
  columnA,
  columnB,
  columnC
FROM
  myTableName;
```

```
SELECT
  *
FROM
  myTableName;
```
Note: the semi-colon is not part of the SQL statement. -> it for PostgreSQL to indicate the end of a statement
