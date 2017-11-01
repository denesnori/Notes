## dictionary

- stores data in key-value pairs
- it is mutable
- each value in the dictionary has a unique key
- dictionaries are unordered

- the key of a dictionary is immutable -> only immutable data types can be keys. Eg. tuples can be keys, but lists can't

-create an empty dictionary:
```
dictA = dict()
dictB = {}
```

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

```
if key in dict:
```

```
if key in dict.keys(): #don't use it, time consuming
```

- ```KeyError``` exception is thrown when a key doesn't exist.

TODO check Python3 .get()


References:
-[](https://stackoverflow.com/questions/10116518/im-getting-key-error-in-python)
- [](https://stackoverflow.com/questions/9285086/access-dict-key-and-return-none-if-doesnt-exist)
