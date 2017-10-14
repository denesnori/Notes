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

### References:
1. (SitePoint on currying)[https://www.sitepoint.com/currying-in-functional-javascript/]
