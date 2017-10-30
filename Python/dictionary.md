## dictionary

- stores data in key-value pairs
- it is mutable
- each value in the dictionary has a unique key
- dictionaries are unordered

- the key of a dictionary is immutable -> only immutable data types can be keys. Eg. tuples can be keys, but lists can't

```
myDict = {
  'name': 'Jane',
  'age': 20
}

myDict['age'] +=1

if 'name' in myDict:
  print myDict['name']
else:
  print 'Not found'
del myDict['age']
```
