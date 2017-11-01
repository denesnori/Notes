## Sets in Python

- set is an unordered collections of unique elements
- it is an unordered collection -> when it is iterated the elements appear in arbitrary order
- a single set contains values of any immutable data type

```
set() #set([])
mySet = list(map(int, raw_input().split()))
set([1,1,1,2,3,4,]) # set([1, 2, 3, 4])
set({
  'score': 3,
  'name': 'Jane',
  }) #set(['score', 'name'])
```

#### Creating sets
```
mySet = {0,1,2,3} # directly assigning values
mySet = set() # initialize an empty set
mySet = set(["a", "b"]) #{"a", "b"}
```

#### Modifying sets

```mySet.add(item)```

- adds a new element to the set
- return ```None```

```
mySet.add(4) # {0,1,2,3,4}
mySet.add(3) # {0,1,2,3,4} nothing happens, already in the set
mySet.add((1,2)) #  {0,1,2,3,4, (1,2)}
```

```mySet.update(iterable)```

- update only works with itrable objects
```
mySet.update(['a','b','c'])
mySet.update({4,5,6,3,7})
mySet.update({13,11},[-1,89])
```

#### Removing items
syntax:
```mySet.discard(item)```
- removes a single value -> returns ```None```
- if the value is not present -> does nothing

```mySet.remove(item)```
- removes a single value -> return ```None```
- if value is not present -> raises a ```KeyError``` exception

```
mySet.discart(1)
mySet.remove(4)
```

```mySet.pop()```
- removes and return an arbitrary element from the set
- if there are no more elements -> raises a ```KeyError``` exception

```
s = set([1])
print s.pop() #1
print s #set([])
print s.pop() # KeyError: pop from an empty set
```

#### Common set operations

```setA.union(setB)``` all the values that exist in a or b
- ```a|b``` == ```a.union(b)```
- operates only on the set of elements is sets


TODO TODO!!!!
```  
s = set('Hello') #
s.union('world') #
s.unions(set('world'))  #
s.uniron(['w','o','r','l','d']) #
s.union(enumerate(['w','o','r','l','d'])) #
s.union({'world':2})
s | set('World')
```

```setA.intersection(setB)``` the values that are present in both a and b
- ```a & b ``` == ```a.intersection(b)```
- only operates on the set of elements in set

```
s = set('Hello')
s.intersection('World')
s.intersection(set('W','o','r','l','d'))
s.intersection(enumerate(['w','o','r','l','d']))
s.intersection({'world':1})
s & set('world')
```


```setA.difference(setB)```
- values that are present in a but not in b
- ```a - b``` == ```a.difference(b)```
```
s = set('Hello')
s.difference('world')
s.difference(set(['w','o','r','l','d']))
s.difference(['w','o','r','l','d'])
s.difference(enumerate(['w','o','r','l','d']))
s.difference({'world':1})
s - set('world')
```
```setA.symmetric_difference(setB)```


- return a set of elements that are either in a or b but not in both.

- ```
```setA.symmetric_difference(setB)``` == ```A^B```

- ```A^B``` only works on set of elements in set

```
s = set('Hello')
s.symmetric_difference('world')
s.symmetric_difference(set(['w','o','r','l','d']))
s.symmetric_difference(['w','o','r','l','d'])
s.symmetric_difference(enumerate(['w','o','r','l','d']))
s.symmetric_difference({'world':1})
s ^ set('world')
```

### set mutations

- union, intersection, difference, symmetric difference don't make any mutations to the set

- ```setA.update(iterable/setB)``` == ```setA |= setB```
- update the set with elements from another iterable or set

```
A = set('Hello')
B = set('World')
A.update(B)
```

- ```setA.intersection_update(iterable/setB)``` == ```setA &= setB)```
- update the set in such way that it only keeps the elements that are both present in the set and the provided iterable/set

```
A = set('Hello')
B = set('World')
A.intersection_update(B)
```
- ```setA.difference_update(iterable/setB)``` == ```setA -= setB```
- update the set in such way that it removes the elements that are both in setA and setB

```
A = set('Hello')
B = set('World')
A.difference_update(B)
```
- ```setA.symmetric_difference_update(iterable/setB)``` == ```setA ^= setB```

- update the set by keeping the elements that can only be found in one of the sets

```
a = { 0, 1 ,2, 3, 4 }
b = { 3 ,4, 5, 6, 7 }
a.union(b) # {0, 1, 2, 3, 4, 5, 6, 7}
a.intersection(b) # {3, 4}
a.difference(b)  # {0, 1, 2}
a^b # calculates symmetric difference
a.symmetric_difference(b)
```

disjoint set: when to sets have no element in common

A strict superset has at least one element that does not exist in its subset

Reference
- [sets](https://www.programiz.com/python-programming/set)


#### Tuples
- immutable!!! -> can't add remove or assign values
- tuples are hashable
- keys in dicitionaries

Swap 2 numbers:
```
a, b = b, a
```
- create an empty tuple: ```()```
- singletopn tupple ```a,``` or ```(a,)```
- comma separated : ```a, b, c``` or ```(a,  b, c)```
- ```tuple()``` or ```tuple(iterable)``` eg. ```tuple([0,1,2])``` -> ```(0,1,2)```

Reference
- [tuples](https://docs.python.org/3/library/stdtypes.html?#tuple)

#### Hash
- ```hash()``` is part of the ```__builtins__``` module -> no need to import it
- return the hash value of an object, if it is defined
- has values are integers
- common usecase: make lookups quick in dictionaries

Reference
- [hash](https://docs.python.org/3/library/functions.html#hash)
