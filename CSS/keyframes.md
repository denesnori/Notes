## CSS3@keyframes

- the animation is created by  gradually changing from one set of css styles to another.

General syntax:
```
@keyframes animationName {
  // css styles
  // either 0-100%
  // or from (===0%) to (===100%)
}
```

Eg.: make an element move gradually 200px down.
```
@-webkit-keyframes mymove {
  from {
        top: 0px;
       }
  to {
      top: 200px;
     }
}

@keyframes mymove {
  from {
    top: 0px;
      }
  to {
    top: 200px;
  }
}
```
