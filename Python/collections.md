## Collections


###  ```collections.Counter()```

- a counter which stores elements as dictionary keys, and their number of occurence as values.

```
from collections import counter

arr = [ 1,2,3,4,4,3,2,1,1,1,2,2,3,3,3,3]
Counter(arr) #{1:,2:,3:,4:}

Counter(arr).items()
Counter(arr).keys()
Counter(arr).values()
```

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
