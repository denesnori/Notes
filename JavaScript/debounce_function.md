### Debounce function
- limita the rate at which a function can fire.
- eg.: resize event listener on the window. Calculates some dimensions and repositions elements. -> one execution is not expensive, but the function being repeatedly fired can slow  the app down --> debounce it. 

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


#### React implemention


```
export default class Demo  extends React.Component {

  constructor(props){
    let debounceTimer = false;
    this.updateHeaderHeight = () => {
      clearTimeout(debounceTimer);
      debounceTimer = setTimeout(this._updateHeaderHeight.bind(this), 400);
      }
    }
}
```
