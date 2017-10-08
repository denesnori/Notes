### requestAnimationFrame

```
function raf (fn) {
  if( !('requestAnimationFrame') in window){
    return fn();
  }
  return requestAnimationFrame(fn);
}
```


## References
- (mdn)[https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame]
- (css tricks)[https://css-tricks.com/using-requestanimationframe/]
