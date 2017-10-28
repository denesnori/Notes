### Very basic stuff

#### Variables
- store a piece of data

```
myVar = 5;
```

#### Whitespace
- it is used to structure the code in Python, whitespace separates statements
-  when the whitespace is off, error messages  are thrown
- the interpreter runs the code line by line and throws errors if necessary
```
def testFunction:
test = 10
return test

print testFunction()
```

```
IndentationError: Expected an indented block
```

```
def testFunction:
  test = 10
  return test

print testFunction()
```

### comments in Python
- single line comments:  ```#```
- multiline comments: triple quotes

```
"""
This is a Python comment
"""
```

### Formatted prints with ```%```
```
firstName = "Jane"
lastName = "Doe"
print "Hello %s %s" % (firstName, lastName)
```

```
total = 33.333333
 print "%.2f" % total
```

## Control flow

```==``` equal
```!=``` not equal
```and```
```or```
```not```

```
if n < 10:
  print "%s is less than 10" % n
```

```
if testFunction():
  #TODO1
  #TODO2
else
  #OTHER THINGS
```

```
if n < 10:
  #TODO
elif n < 100:
  #TODO
else:
  #TODO
```

```
def myFunnction(n):
  #do stuff
  #do more stuff

myFunction(5)
```

```
# Python 2
if __name__ == '__main__':
  a = int(raw_input())
  b = int(raw_input())

# Python 3
a = int(input())
b = int(input())
```

### ```__future__``` statements
Future statements define how the Python module is parsed. -> they need to be at the top of the file.

```__future__``` is a pseudo-module which can be used to enable language features which are not compatible with the dcurrent interpreter.

```from __future__ import division```

```
from __future__ import division
print 4/3 # print 1.33333
print 4/3 # print 1
```

without importing ```__future__``` both would print 1. Since without importing ```__future__```, ```/``` is mapped to ```__div__()``` method, when ```__future__``` is present it is mapped to ```__truediv__()```.

```//``` is always mapped to ```__floordiv__()```.

```
from __future__ import division
if __name__ == '__main__':
  a = int(raw_input())
  b = int(raw_input())
  print a//b   
  print a/b
```

Reference:

- [stackoverflow](https://stackoverflow.com/questions/7075082/what-is-future-in-python-used-for-and-how-when-to-use-it-and-how-it-works)
