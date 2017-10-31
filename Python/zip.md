## ```zip(iterables)```

- input iterables (list, string, dic, user defined iterables) (zero or more)
- return iterator of tuples -> which aggregates the elements from the interables passed
- if there are more than one input iterators, the iteration stops when the shortest iterator is exhausted

```
zip() # empty iterator []
zip([1,2,3]) # iterator of 1 tuples [ (1), (2), (3)]
zip([1,2,3,], ["a","b","c","d","e"]) # [ (1, "a"), (2, "b"), (3, "c")]
```
**unzip the values**

- you can use the * operator to unzip a list
```
zip(*zippedList)
```
```
numbers = [1,2,3,4]
letters = ["a","b","c","d","e"]
res = zip(numbers, letters)
print res #[(1, 'a'), (2, 'b'), (3, 'c'), (4, 'd')]
n,l = zip(*res)
print n #(1, 2, 3, 4)
print l #('a', 'b', 'c', 'd')
```

#### References
- [](https://www.programiz.com/python-programming/methods/built-in/zip)
