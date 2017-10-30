# Map, filter, Reduce
Facilitate a functional approach to programming.
```
n = int(raw_input())
grades = [  [raw_input(), float(raw_input())] for _ in  range(n)]

secondLowest = sorted(list(set([marks for name, marks in grades])))[1]
grades = sorted(grades, key = lambda x:x[1])
print ('\n').join([name for name,mark in grades if mark == secondLowest ])

```

## Map
````map``` calls the provided function on every item in the array, return a new array.

```
map( function-to-apply, array)
```

Without map:
```
arr = [1,2,3]
double = []
for i in arr:
  double.append(i * 2)
```

With map:
```
arr = [1, 2, 3]
double = list(map(lambda x: x*2, arr))
```

Apply a list of function on an array:
```
def double(x):
  return 2*x

def square(x):
  return x**2
def addOne(x):
  return x+1

functions = [double,square,addOne]
for i in range 5:
  value = list(map(lambda x: x(i), functions)) # call the functions!
  print value
  ## [0, 0, 1] ...
```

## Filter

## Reduce

## foreach - not in python
- only foreach style ```for``` loop.

```
for x in arr:
  print x
```

Reference:
-[stackoverflow](https://stackoverflow.com/questions/40346498/python-foreach-equivalent)

## Filter

Returns those elements from an array that satisfy the given conditions.

```
arr = [1,2,3,4,5]
unique = list(filter(lambda x: x%2==0, arr))
```
## Reduce

```
from functools import reduce
sum = reduce((lambda x,y: x+y), [1,2,3])
```

### References:
- [](http://book.pythontips.com/en/latest/map_filter.html)
