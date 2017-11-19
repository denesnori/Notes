## Collections


###  ```collections.Counter()```

- a counter which stores elements as dictionary keys, and their number of occurrence as values.

```
from collections import counter

arr = [ 1,2,3,4,4,3,2,1,1,1,2,2,3,3,3,3]
Counter(arr) #{1:,2:,3:,4:}

Counter(arr).items()
Counter(arr).keys()
Counter(arr).values()
```

```
#!/bin/python3

import sys
from collections import Counter
if __name__ == "__main__":
    s = sorted(input().strip().split())
    c = Counter(*s)
    m = c.most_common(3)
    for el in sorted(c.items(), key=lambda x: (-x[1], x[0]))[:3]:
        print('%s %s'%(el[0],el[1]))
```

### Ordered counter

Reference:
-[](https://codefisher.org/catch/blog/2015/06/16/how-create-ordered-counter-class-python/)

### ```collections.defaultdict(datatype)```

- very similar to dictionaries
- one difference: when you initialize it, you have specify the value field's data type

```
from collections import defaultdict

d = defaultdict(list)
d['first'].append('a')
d['next'].append('Hey!')
d['first'].append('b')
for i in d.items():
  print i # prints key - value tuples
```

### ```collections.namedtuple()```
- object types
- turns tuples into convenient containers whatever it means XD
- for namedtuples you don't need to use integer indices to access members

```
from collections import namedtuples
Point = namedtuple('coordinate', 'x,y')
first = Point(0,0)
second = Point(1,0)
res = (first.x * second.x)+(first.y * second.y)
```

```
from collections import namedtuple
House = namedtuple('House','Rooms Colour Windows')
myHome = House(Rooms = 2, Colour = 'white', Windows=4)
```

### ```collections.OrderedDict()```
- remembers the order in which the keys were added
- if the corresponding value for a key is overwritten, the original position is unchanged.

```
from collections import OrderedDict

ordinary_dictionary = {}
ordinary_dictionary['a']=1
ordinary_dictionary['b']=2
ordinary_dictionary['c']=3
ordinary_dictionary['d']=4
ordinary_dictionary['e']=5

print ordinary_dictionary
# {'a': 1, 'c': 3, 'b': 2, 'e': 5, 'd': 4}

ordered_dictionary = OrderedDict()
ordered_dictionary['a']=1
ordered_dictionary['b']=2
ordered_dictionary['c']=3
ordered_dictionary['d']=4
ordered_dictionary['e']=5
print ordered_dictionary #OrderedDict([('a', 1), ('b', 2), ('c', 3), ('d', 4), ('e', 5)])
```

### ```collections.dequeue()```
- a dequeue is a double ended queue -> one can add or remove elements to/from both ends.

- O(1) performance for appends and pop on both ends

```
from collections import deque

d = deque()
d.append(1)
d.appendleft(2)
d.clear()
d.extend(1)
d.extendleft('234') # ['4','3','2','1']
d.count('1')
d.pop()
d.popleft()
d.extend('7896')
d.remove(2)
d.reverse()
d.rotate(3) #['8','7','3','6','9']
```
```
from collections import deque
n = int(input())
d = deque()
for _ in range(n):
    next = input().split()
    getattr(d,next[0])(*next[1] if len(next)>1 else [])
print(*[i for i in d])
```

Reference:
-[dequeue methods](https://docs.python.org/2/library/collections.html#deque-objects)
-[dequeue recipes](https://docs.python.org/2.7/library/collections.html#deque-recipes)
