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

### append a dictionary to a dictionary

```
orig.update(extra)
```

If we don't want orig to be modified, then we should make a copy first.

```dict.copy()``` makes shallow copies in python.

```
dest = dict(orig) # same as orig.copy()
dest.update(extra)
```
OR use ```chain```
```
from itertools import chain

dest = dict(chain(orig.items(), extra.items()))
```
OR without itertools

```
dest = dict(list(orig.items())+list(extra.items()))
```
OR

```
dest = {**orig, **extra}
```
```
dest = {**orig,'D':4, 'E':5}
```
Note: if the two dicts have overlapping keys, the value for the key in extra will overwrite the value in dest.

```
a = {
  1:1,
  2:2,
  3:3
}
b = {
  1: 'a',
  4: 'd'
}
a.update(b)
#{
#    1:'a',
#    2:2,
#    3:3,
#    4:'d'
#}
```

References:
-[](https://stackoverflow.com/questions/10116518/im-getting-key-error-in-python)
- [](https://stackoverflow.com/questions/9285086/access-dict-key-and-return-none-if-doesnt-exist)
-[](https://stackoverflow.com/questions/8930915/append-dictionary-to-a-dictionary)
