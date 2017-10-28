## Sets in Python

#### Arrays

- create an empty list
```
arr = list()
arr = []
```
- access an element of an array
```
arr[0]
```

**Array methods**

1. ```arr.append(item)```
- add an element to the end of an Array

```
arr = [0,1,2]
arr.append(3)
print arr # [0,1,2,3]
```

2. ```arr.extend(list)```
- concatenates two lists

```
arr = [0,1,2]
arr.extend([3,4,5])
print arr # [0,1,2,3,4,5]
```

3. ```arr.insert(index, item)```
```
arr = [0,1,2]
arr.insert(0,-1)
print arr
# [-1,0,1,2]
```
4. ```arr.remove(item)```

```
arr = [0,1,2,3]
arr.remove(1)
print arr # [0,2,3]
```

5. ```arr.pop()```
- removes the last item of the array
```
arr = [0,1,2,3]
var last = arr.pop()
print last # 3
```
6. ```arr.index(3)```
- returns the first index of a value in the array
- if there is no match, return an error
```
var arr = [0,1,2,3]
ind = arr.index(3)
print index #3
```

7. ```arr.count(item)```
- number of occurences of ```x``` in the list
```
var arr = [0,1,1,2]
var count = arr.count(1)
print count # 2
```

8. ```arr.sort()```
```
var arr = [1,3,0,2]
arr.sort()
print arr $ [0,1,2,3]
```

9. ```arr.reverse()```
```
var arr = [0,1,2,3]
arr.reverse()
print arr # [3,2,1,0]
```
