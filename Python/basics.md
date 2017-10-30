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

### __name__ == '__main__'

- when the Python interpreter reads the source file, it executes all the code inside.
- BUT! First it defines some special variables.

1. The python interpreter runs our source file as the main program

```
python myExample.py
```
 Then it sets the ```__name__``` variable to have a value ```__main__```.

2. Our file is imported inside another file, module

```__name__``` is set to the module's name.

Simple example:

```
# a.py
import b
```

```
# b.py
print "Called from %s" % __name__
if __name__ == '__main__':
  print "Called again from from %s" % __name__
```

```
$ python a.py
Called from b
```

```
$ python b.py
Called from __main__
Called again from __main__
# globals()['__name__'] is set to '__main__' this time
```


Reference:
- [stackoverflow](https://stackoverflow.com/questions/419163/what-does-if-name-main-do)

### ```__future__ import print_function```

Brings the ```print``` function from Python 3 into Python 2.6+.

```
print(x, sep=' ', end='')
```
```
from __future__ import print_function

def printNumbers(n):
  for i in range(1, n+1):
    print(i, sep='',end='')

if __name__ == '__main__':
  n = int(raw_input())
  printNumbers(n)
```

Reference:
[stackoverflow](https://stackoverflow.com/questions/32032697/how-to-use-from-future-import-print-function)

### for loops
```
for x in  range(0,3):
  print "The next number is %d" % (x)
```


### simple sort functions

- ascending order

```
def compare(x,y):
  if x < y:
    return -1
  elif x > y:
    return 1
  else:
    return 0
```
- descending order
```
def compare(x,y):
  if x > y:
    return -1
  elif x < y:
    return 1
  else:
    return 0
```
