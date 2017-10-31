### List comprehensions in Python
- elegant and succint way of building building lists without ```for``` loops

**[ expression-involving-loop-variable for loop-variable in sequence]**

```
list = [ x for x in range(5) ]
# [0,1,2,3,4]
squareList = [ x**2 for x in range(5) ]
# [0,1,4,9,16]

```
**[ expression-involving-loop-variables for outer-loop-variable in outer-sequence for inner-loop-variable in innner-sequence ]**

```
results = []

for i in outer_range:
  for j in inner_range:
    results.append( something fancy )
```

**[ expression-onvolving-loop-variable for loop-variable in sequence if boolean-expression-involving-loop-variable ]**

```
evenNumbers = [ x for x in range(10) if x % 2 == 0 ]
#[0,2,4,6,8]
```

### Dont push to github below this
Task: you are given to integers, x and y. You need to find out the ordered pairs (i, j), such that (i+j) is not equal to n and print them lexicographic order ( 0 <= i <= x) and (0<=j<=y).

Solution without list comprehensions:

```
x = int( raw_input() )
y = int( raw_input() )
n = int( raw_input() )
arr  = []
p = 0
for i in range ( x + 1 ):
  for j in range ( y + 1 ):
    if i+j != n:
      arr.append([])
      arr[p] = [ i, j ]
      p += 1
print arr
```
With list comprehensions:
```
x = int( raw_input() )
y = int( raw_input() )
n = int( raw_input() )
print [ [ i, j ] for i in range ( x + 1 ) for j in range( y + 1 ) if ( ( i + j) != n ) ]
```

### References
- [hackerrank](https://www.hackerrank.com/challenges/list-comprehensions/tutorial)
- [thelearningpoint](http://www.thelearningpoint.net/computer-science/learning-python-programming-and-data-structures/learning-python-programming-and-data-structures--tutorial-15--generators-and-list-comprehensions)
