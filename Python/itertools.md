## itertools


#### ```itertools.product(a,b)```
 - return the Cartesisan product of the itereables

``` product(a,b)``` == ```((x,y) for x in a for y in b)```

 ```
 from itertools import product

list(product([1,2 ], repeat = 2)) # [(1,1), (1,2), (2,1), (2,2)]

list(product([1,2,3],[4,5])) # [(1,4),(2,4),(3,4),(1,5), (2,5), (3,5)]

a = [ [1,2,3], [4,5]]
 list(product(*a)) # [(1,4),(2,4),(3,4),(1,5), (2,5), (3,5)]

 b =  [ [1,2,3], [4,5], [6,7]]
 list(product(*b))
 ```

Reference:
-[Cartesian product - Wikipedia](https://en.wikipedia.org/wiki/Cartesian_product)

#### ```itertools.permutations(iterable[, r])```
- returns all permutations of length ```r```
- if ```r``` is not defined, or ```None``` -> ````r``` defaults to the length of the array
- permutations are returned in lexicographic order -> if the input is sorted, the returned permutation tuples will be sorted too

```
from itertools  import permutations
print permutations([1,2,3]) # not human readable permutations object

print list(permutations([1,2])) # [(1,2), (2, 1)]

list(permutations([1,2,3,4],2))

list(permutations('abcdef',2))
```

### ```iteratedools.combinations(iterable, r)```
- 'r' is required
- return combinations of ```r``` length
- the returned combinations are in lexicographic order -> if the input is sorted, so is the result

```
from itertools import combinations

list(combinations('12345',2)) # [('1','2'), ('1','3')...]
list(combinations([1,1,22],3)) #
```

### ```itertools.combinations_with_replacement(iterable,r)```
- return subsequence of length ```r``` where elements can be repeated
- result is returnded in lexicographic order -> if the input is sorted, the result is sorted

```
from itertools import combinations_with_replacement

list(combinations_with_replacement('1234',2))

list(combinations_with_replacement([1,1,2,2,3],2))
```

### ```itertools.groupby(iterable[,key])```

- counts consecutive occurences

12233332 -> (1, 1) (2, 2) (4,3) (1,2)
```
from itertools import groupby
print(*[(len(list(c)), int(k)) for k,c in groupby(input())])
```
Reference:
-[](https://docs.python.org/2/library/itertools.html#itertools.groupby)
-[](https://stackoverflow.com/questions/773/how-do-i-use-pythons-itertools-groupby)


-[](https://docs.python.org/2/library/itertools.html)
