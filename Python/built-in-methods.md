## built-in methods


### ```divmod(a,b)```
- built-in functional
- takes a,b and returns a tuple with the quotien of a/b and the remainder

```
divmod(11,3) # (3, 2)
```

## ```pow(a,b)``` and ```pow(a,b,m)```
- in python integeres can be as big as the bytes in our computers memory! No limit!

```pow(a,b)``` == ```a**b```

```pow(a,b,m)``` -> translates to a**b mod m

#### ```sorted(iterable[, key][, reverse])```

- iterable: sequence(string, tuple, list) or collection (set, dictionary, frozen set)
- reverse (optional): if it its true, sorted to descending order
-key (optional): serves as key for comparison

- returns a sorted list
