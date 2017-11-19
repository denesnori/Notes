## ```IN```

- used in the ```WHERE``` clause to check if a value matched any of the provided values

Syntax:
- it can be a list of values
```
value IN (value1,value2, ...)
```
or
```
value NOT IN (valueA,valueB,valueC,...)
```
- or it can be a  ```SELECT``` statement, which is called a subquery (a query inside another query)
```
value IN (SELECT value FROM myTableName)
```
