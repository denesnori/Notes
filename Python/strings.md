## Everything string related

### textwrap module

- ```textwrap.wrap(string, width)```
 wraps a text that a line's length is at most width.
 ```
 import textwrap
 string = "An example sentence that can be wrapped"
 print textwrap.wrap(string,7)
 # ['An', 'example', 'sentenc', 'e that', 'can be', 'wrapped']
 ```
- ```textwrap.fill(string, width)```
return a single sting with the wrapped paragraph
```
import textwrap
string = "An example sentence that can be wrapped"
print textwrap.fill(string,7)
# An
# example
# sentenc
# e that
# can be
# wrapped
```

## string formatting

#### converting numbers to different bases

```
print "int: {0:d}".format(42) # 'int: 42'
print "hex: {0:x}".format(42) # 'hex: 2a'
print "oct: {0:o}".format(42) # 'oct: 52'
print "bin: {0:b}".format(42) # 'bin: 101010'

print str(42)
print oct(42)
print hex(42)
print bin(42)

print "{0:{width}o}".format(17, width=5) # '   21' # right aligned
```

Reference:
[](https://docs.python.org/3/library/string.html)
