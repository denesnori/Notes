### Currying

Partial application of a functions arguments.
-->
- either pass all the arguments in one go and get the result back,
- or pass a subset of the argiments first, get a function back that expects the rest of the arguments.

```
var curry = function ( uncurried ){
  var params = Array.prototype.slice.call(arguments,1);
  return function () {
    return uncurried.apply(this, params.concat(Array.prototype.slice.call(arguments,0)))
  }
}
```

## Currying vs partial application



### References:
1. (SitePoint on currying)[https://www.sitepoint.com/currying-in-functional-javascript/]
2. (Eric Elliott - Medium -- currying vs partial application)[https://medium.com/javascript-scene/curry-or-partial-application-8150044c78b8]
