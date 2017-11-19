Python strings are immutable
- change a python string:
a, convert it to an array, then change the value
```
string= 'I am a python string'
array = string.split(' ')
#then you can do something with the array
array[1] = 'new'
print (' ').join(array)
```

b, slice the string ang join it again

```
string = 'I am a python string'
string = string[:5]+'new stuff'+string[6:]
```

### String methods in Python

### ```len()```
```
name = Lilla

print len(name)
```

### ```string.lower()```
```
name = Lilla

print name.lower()
```

### ```string.upper()```

```
name = Lilla

print name.upper()
```

### ```str()```
- transforms non-strings into strings
```
str(11)

# "11"
```
### ```string.find(sub_string, beg=0, end=len(string))```

- return value: index or -1

```
"example".find('am') # 2
```

[](https://www.tutorialspoint.com/python/string_find.htm)

### ```str.index(str, beg = 0, end = len(string))```

- same as find
- BUT! raises an exception when the sub_string is not found

[](https://www.tutorialspoint.com/python/string_index.htm)

### Dot notation

```len()``` and ```str()``` can work on other datatypes, while the methods that use the dot notation only work with strings.

## ```string.split(delimiter)```

```
example = 'This is a sentence'
print example.split(' ')
```

## ```(delimiter).join(array)```

## ```string.find(substring)```

Gives the first index of a match.

## ```string.isalnum()```
- built-in method
- checks whether the string contains only alphanumeric characters (a-z, A-Z, 0-9)

## ```str.isalpha()```
- checks if all the characters are alphabetical (a-zA-Z)

## ```str.isdigit()```
- checks whether all the chars are digits

## ```str.isupper()```
- all the chars are in lower case

## ```str.isupper()```
- all the characters are upper case

## String alignment
```
string.ljust(width) # left aligned string of length width
string.center(width) # centered string of length width
string.rjust(width) # right aligned string of length width
```

```
width = 10
print 'Name'.rjust(width,'*') #******Name
```


## ```string.capitalize()```
s = input()
for x in s[:].split():
    s = s.replace(x, x.capitalize())
print(s)

## str.strip(pattern)
- removes leading or trailing characters that match any character from the given string.

```
".. ,,,:::Hello! ,,.,.,;,.,".strip(".:,; ") # Hello!
```


### References
- [](http://www.thelearningpoint.net/computer-science/learning-python-programming-and-data-structures/learning-python-programming-and-data-structures--tutorial-12--string-manipulation)
