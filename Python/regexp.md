## Regular expressions in python
- provided by the ```re``` module in python
- raw strings should be provided like: ```r'strings'```
- a regex is sequence that defines a search pattern

#### ```re.search(pattern, string)```

- looks for the first location where the pattern matches
- return value: ```MatchObject``` or ```None```

```
import re
print bool(re.search(r'lo','hello')) #True
```

#### ```re.match(pattern, string, flags = 0)```
- **only matches at the beginning of a string**
- success: ```MatchObject```
- failure: ```None```
- match object methods:
  - group(num = 0) -> returns the entire match or a specific subgroup
  - groups() -> returns subgroups in a tuple

Match floats:
```
import re
[ print(bool(re.match(r'^[=-]?[0-9]*?\.[0-9]+$',input()))) for _ in range(int(input()))]
```
```*``` whatever it follows it can repeat arbitrarily times, 0 - multiple times.

#### ```re.split(pattern, string)```

- splits a string on a pattern

```
import re
re.split('@', 'somebody@something.com')
```

Split and filter empty strings:

- filter only returns the elements that evaluate to True
- ```None``` used as the first argument removes all the elements that evaluate to False

```
import re
print(*filter(None, re.split(r'[.,]+', input())), sep = '\n')
```


#### ```group()```, ```groups()``` and ```groupdict()```

**group()**
- returns one or more subgroups of a match

```
import re
match = re.match(r'(\w+)@(\w+)\.(\w+)', 'username@something.com')
match.group(0) # the entire match 'username@something.com'
match.group(1) # capture group 1
match.group(2) # capture group 2
match.group(3) # capture group 3
match.group(1,2,3) # can accept multiple arguments , returns a tupe ('username', 'something', 'com')
```

**groups()**
- returns a tuple containing all subgroups of the match

```
import re
match = re.match(r'(\w+)\1@(\w+)\2\.(\w+)\3', 'username@something.com') # \1 is a backreference to capture group 1 , and so on...
match.groups() # returns a tupel ('username', 'something', 'com')
```
**groupdict()**
-return a dictionary containing all the named subgroups of a match

```
import re
match =  re.match(r'(?P<user>\w+)@(?P<website>\w+)\.(?P<extension>\w+)','username@something.com') # {'website': something, 'user':'username','extension':'com'}
```

#### ```re.findall()``` and ```re.finditer()```

**```re.findall(pattern, string)```**

- finding all instances of a pattern
- return non-overlapping matches as a list
- if one or more groups are present in the pattern, return a list of groups
- return a list of tuples if there are more than one groups



```
import re
re.findall(r'\w', 'hello')
#['h','e','l','l','o']
```
match ip addresses example:

```
import re

ip = "blah blah 192.168.0.185 blah blah"

regexp = '(\d{1,3}\.){3}\d{1,3}'
print(re.search(regexp,ip).group()) #192.168.0.185
print(re.search(regexp,ip).groups()) # ('0.',)

print(re.findall(regexp,ip)) # ['0.']

regexp = '(?:\d{1,3}\.){3}\d{1,3}'
print(re.findall(regexp,ip)) # ['192.168.0.185']
```


**```re.finditer(pattern, string)```**

- return an ```Iterator Object```  yielding ```MatchObject``` for all the non-overlapping matches.

```
import re
re.finditer(r'\w', 'hello')
map(lambda x: x.group(), re.finditer(r'\w', 'hello'))
```

#### ```re.start()``` and ```re.end()```

- return the start and end indices of the substring matched by the regexp

```
import re
m = m.search(r'\w+','abcd')
m.start() #0
m.end() #3
```

**TODO find the difference between re.search and search .e.g.: re.search can't take flags for start indices? is that true?**

```
import re

s = input()
sub = input()

pattern = re.compile(sub)
match = pattern.search(s)
if not match:
  print("(-1,-1)")
while r:
  print("({0} {1})".format(r.start(), r.end()-1))
  match = pattern.search(s, match.start()+1)
```

#### Search and replace ```re.sub(pattern, replacement, string, max=0)```

- replace all occurrences of the  pattern with replacement unless max is provided

```
n = re.sub(r'-', '', n)
```

#### Regex substitution ```re.sub(pattern,function,string)```

- ```re.sub()``` matches a pattern, and for every match  calls a function
- returns the modified string as an output

```
import re

def cubic(match):
  n = int(match.group(0))
  return str(n**3)

print(re.sub(r'\d+', cubic, '0 1 2 3'))
```

Remove comments from HTML:

```
import re

html = """
<html>
  <head>
    <title>HTML</title>
  </head>
  <body>
    <!-- My super fancy comment comes here!!! -->
  </body>
</html>
```
print(re.sub(r"<!--.*? -->","",html)) # removes comment

#### flags

- ```re.I```: case-insensitive
- ```re.L```:
- ```re.M```:
- ```re.S``` == ```re.DOTALL```: without this flag ```.``` matches anything BUT a newline. With this flag, the regexp matches newlines too. Good for multiline searches.
- ```re.U```:
- ```re.X```

Reference:
-[](https://stackoverflow.com/questions/23464619/passing-in-flags-as-an-argument-to-re-compile)

#### named groups

```
p = re.compile(r'(?P<year>\b\d{3,4}\b)',re.I)
match = p.search('12 1293 2324 21424 24234')
match.group('word') # pick the capture group by name
match.group(1) # same as before
```

#### general regexps

**positive lookahead ```r'(?=expression)'```**

- when you want a pattern followed by a specific expression
eg.: for finding overlapping occurences

```
re.search(r'Stephen (?=Hawking)','Stephen Hawking')
```

Reference:
-[lookahead](https://www.hackerrank.com/external_redirect?to=http://www.regular-expressions.info/lookaround.html)

**negative lookahead ```(?!expression)```**
- you want a pattern to be followed by anything but a certain expression


**positive lookbehind** ```?<=()```
- check if the current positions in the string preceded by whatever is inside ```?<=()```
-check if the argument is true, but doesn't consume it

```re.search(r'(?<=abc)def','abcdef')```

Reference:
-[](https://docs.python.org/3/library/re.html#module-re)

**negative lookbehind** ```?<!()```

- a pattern preceded by anython but a certain expression

#### email validation example with and without the use of regexps

//Not OK YET

```
def isValid(email):
  try:
    username, url = email.split("@")
    website, ext = url.split('.')
  except Exception: #ValueError
    return False

  if usrname.replace(r'[_-]', "").isalnum() is False:
    return False
  elif not website.isalnum():
    return False
  elif len(extension > 3):
  return False
  else:
    return True

n = int(input())
emails = [input() for _ in range(n)]

valid = list(filter(isValid, emails))
```

Regexp to look for valid email addresses:

```\w``` allows [a-z0-9_]

```\b``` metacharacter is used to find a match at the beginning or at the end of a word. If there is no match, returns null.

```
pattern = re.compile("^[a-z][\w-.]*@[a-z0-9]+\.[a-z]{1,3}", re.I)
```
**Non-capturing group parentheses** ```(?:...)```
- matches the expression in the parantheses, BUT the substing matched by the group cannot be retrieved after performing the match and cannot be backreferences later in the pattern

example:

```
import re

regexp = re.compile('(MRS|MR) (\\w+) (\\w+)')
print(regexp.match('MR JOHN DOE').groups()) #('MR', 'JOHN', 'DOE')
```
Whatever is inside a parenheses is captured by ```.groups()```. If you don't care about one or more of the groups, you can put them inside a non-capturing parentheses by adding a ```?:``` at the beginning.

```
import re

regexp = re.compile('(?:MRS|MR) (\\w+) (\\w+)')
print(regexp.match('MR JOHN DOE').groups()) #( 'JOHN', 'DOE')
```

Reference:
- [](https://stackoverflow.com/questions/22989241/python-re-example)
- [](https://stackoverflow.com/questions/10793504/what-does-mean-in-a-python-regular-expression)

** Not match the start of a line**  ```(?<!^) ```

Regexp to match hex-color codes

```
11
#BED
{
    color: #FfFdF8; background-color:#aef;
    font-size: 123px;
    background: -webkit-linear-gradient(top, #f9f9f9, #fff);
}
#Cab
{
    background-color: #ABC;
    border: 2px dashed #fff;
}
```

```(?<!^)``` -> don't catch the ids

```
(?<!^)(#(?:[\da-f]{3}){1,2})
```

```
[hex(re.findall(r'(?<!^)(#([0-9a-f]{3}){1,2})',input(),re.I)) for _ in range(n)]
```
**HTML
Hypertext Markup Language is a standard markup language used for creating World Wide Web pages.

Parsing
Parsing is the process of syntactic analysis of a string of symbols. It involves resolving a string into its component parts and describing their syntactic roles.

HTMLParser
An HTMLParser instance is fed HTML data and calls handler methods when start tags, end tags, text, comments, and other markup elements are encountered**

### email validation library TODO, dont forget to look it up

##### Search for 3 or more consecutive same numbers

```((\d)\2{2,})```  backreference the 2nd capture group

```
import re

s = '469997453444421'
re.findall(r'((\d)\2{2,})',s) # [('999', '9'), ('4444', '4')]
[match[0] for match in re.findall(r'((\d)\2{2,})',s)] #['999','4444']
```
** Convert a RegExp search to a boolean value **

```
import re
bool(re.search('ba[rzd]', 'foobarrrr')) # True
```
OR
```Match Objects``` are always ```True``` -> test for ```None```

```
st = "bar"
 m = re.search(r"ba[r|z|d]",st)
if m is not None:
     m.group(0) # 'bar'
```

#### Validating UID

- It must contain at least  uppercase English alphabet characters.
- It must contain at least  digits ( - ).
- It should only contain alphanumeric characters ( - ,  -  &  - ).
- No character should repeat.
There must be exactly  characters in a valid UID.

```
import re

def test(s):
    if not s.isalnum():
        print('Invalid')
    elif len(set(s)) < len(s) or len(s) != 10:
        print('Invalid')
    elif(len(re.findall(r'[A-Z]',s))<2):
        print('Invalid')
    elif len(re.findall(r'\d',s)) <3:
        print('Invalid')
    else:
        print('Valid')



n = int(input())

l = [ input() for _ in range(n)]
for s in l:
    test(s)
```


```
import re
for _ in range(int(input())):
    s = input()
    print('Valid' if all([re.search(r, s) for r in [r'[A-Za-z0-9]{10}',r'([A-Z].*){2}',r'([0-9].*){3}']]) and not re.search(r'.*(.).*\1', s) else 'Invalid')
```

### Roman numerals with regexp

```
import re

thousand = 'M{0,3}'
hundred = '(C[MD]|D?C{0,3})'
ten = '(X[CL]|L?X{0,3})'
digit = '(I[VX]|V?I{0,3})'
print (bool(re.match(thousand + hundred+ten+digit +'$', input())))
```


Reference:
- [](https://stackoverflow.com/questions/267399/how-do-you-match-only-valid-roman-numerals-with-a-regular-expression)

#### References

-[](https://www.tutorialspoint.com/python/python_reg_expressions.htm)
