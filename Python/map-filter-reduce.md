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
````map``` calls the provided function on every item in the array, returns a new array.

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

```
list(map(len, [ 'Jane', 'Jen', 'James']))
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

**lambda**
- single expression anonymous function
- often inline function
- popular in functional and GUI programming
- cannot use return statements
- can only have a single expression
- creates a function and returnd the function <--> ```def``` creates a function and assings it a name
- can be used inside lists or dicts

```
sum = lambda x,y: x+y
sum(1,2) #3
```

## Filter


## Reduce

```
tuples = ((1,2),(3,4), (5,6))
reduce( lambda acc,curr: acc+curr, tuples, ()) # (1,2,3,4,5,6)
```

Reference:
- [](https://stackoverflow.com/questions/13603361/python-reduce-explanation)

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
-[](https://www.python-course.eu/lambda.php)
