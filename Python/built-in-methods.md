## built-in methods


### ```divmod(a,b)```
- built-in functional
- takes a,b and returns a tuple with the quotien of a/b and the remainder

```
divmod(11,3) # (3, 2)
```

## ```pow(a,b)``` and ```pow(a,b,m)```
- in python integers can be as big as the bytes in our computers memory! No limit!

```pow(a,b)``` == ```a**b```

```pow(a,b,m)``` -> translates to a**b mod m

##### ```input()``` in Python 2
In Python 2, ```input()``` == ```eval(raw _input(prompt))```


 - read the value for the x variable
 - rad the expression (note the variable should have the same name )
```
# 1 2
# x**2 + x
x,res = map(int,raw_input().split())
print input()==res
```
#### ```eval(expression)```
-evaluates an expression, python statement or object

```
eval('1+1') #2
x = 2
eval('x+2') #4
```
```
type(eval(len)) # built in function or method
type(len) #'str'
```

#### ```sorted(iterable[, key][, reverse])```

- iterable: sequence(string, tuple, list) or collection (set, dictionary, frozen set)
- reverse (optional): if it its true, sorted to descending order
- key (optional): serves as key for comparison

- returns a sorted list

// TODO read on sorted with key lambda

```
  print(sorted(arr,key=lambda x: x[k]))
```

```
print(*sorted(input(), key=lambda c: (-ord(c) >> 5, c in '02468', c)), sep='')

print(*sorted(input(), key=lambda c: (c.isdigit() - c.islower(), d, c)), sep='')

order = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1357902468'
print(*sorted(input(), key=order.index), sep='')

import string
print(*sorted(input(), key=(string.ascii_letters + '1357902468').index), sep='')
```
Reference:
-[sorted with key](https://stackoverflow.com/questions/8966538/syntax-behind-sortedkey-lambda)
-[](https://stackoverflow.com/questions/32238196/how-does-the-key-argument-in-pythons-sorted-function-work)

### ```any()```
- return True if any of the elements is true
- it the iterable is empty -> returns false

```
any([10<5, 1>9, 8>2]) #True
any([3<1,3>99]) #False
```
### ```all()```
- returns true id all the elements are true
- empty iterable returns true
```
any([10<5, 1>9, 8>2]) #False
any([3>1,3<99]) #True
```
```
k = input()
arr = input().split()
print(all(int(i) >0 for i in arr) and any(k[::-1]==k for k in arr))

```
