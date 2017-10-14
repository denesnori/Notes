### Mutating methods

- copyWithin()
- fill()
- pop()
- push()
- reverse()
- shift()
- unshift() // adds an item at the beginning of an array
- sort()
- splice()


### slice vs splice

slice: non-mutating, up to 2 args

splice: mutating,  n args

**Array.splice()**
- mutates the original array by adding or removing items.
- return value: an array containing the deleted elements. If no elements are removed, an empty array is returned.

```
array.splice(start) // deletes everything from start
array.splice(start,deleteCount) // removes items
array.splice(start, deleteCount, items) // adds items
```
