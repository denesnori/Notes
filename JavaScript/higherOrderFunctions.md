### Higher-order function
A function that can take another function as an argument, or that return a function as a result.


### forEach

The `forEach` method executes callback function once for each array element.

Syntax: ```array.forEach(callback(current,index,array), thisArg)```

```
const arr = [1,2,3];

arr.forEach((current)=>{
  console.log(current)
  })

```

return value: ```undefined```


#### Array.prototype.find(callback[, thisArg])

- Return the first item that matches the test condition inside the callback function.
- if there is no match, return ```undefined```.

```
[1,2,3,4,5,6,7].find((item,index,array)=> item > 4) //=> 5

```

#### Array.prototype.findIndex(callback[, thisArg])

- returns the *index* of the first item that matches the condition in the callback.
- if there is no match, ```-1``` is returned.
```
[1,2,3,4,5,6,7].findIndex((item,index,array) => {
  return item > 4
  }) // => 4
```
