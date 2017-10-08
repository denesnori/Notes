### Debounce function

```
function debouncer(func, wait, asap){
  var timeout;
  return function(){
    var obj = this, args = arguments;
    function delayed(){
      if(!asap){
        func.apply(obj,args);
        timeout =null;
      }
    }
    if (timeout){
      clear(timeout)
    }
    if(asap){
      func.apply(obj,arguments);
    }
    timeout = setTimeout(delayed, wait)
  }
}

debouncer((num)=>{console.log("hi",num)},500,false)(400)
```
