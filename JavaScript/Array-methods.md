## Array.methods()

### Array.prototype.includes()
- determines whether an array includes an element
- return value: true / false

```
arr.includes(searchElement)
```

```
arr.includes(searchElement, fromIndex)
```

```
const a = [0,1,2,3,4,5,6,7,8,9];
a.includes(5); // true
a.includes(11); //false
a.includes(9,10); //false
a.includes(9,-1); //true
[0,1,2,NaN].includes(NaN); //true
```

### Array.prototype.indexOf()
