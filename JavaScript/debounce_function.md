### Debounce function
- limita the rate at which a function can fire.
- you want the function to execute  only once after a defined time interval. -> if the event occurs more than once within the interval, the interval is reset each time.
- exmample1: resize event listener on the window. Calculates some dimensions and repositions elements. -> one execution is not expensive, but the function being repeatedly fired can slow  the app down --> debounce it.
- example2: a user is typing into an input field, and you want to execute a function (eg. server call), when the user stops typing for a certain time (eg.500ms)

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

### Throttle function
- a function that you want to execute periodically with an interval between each execution.
- the user is typing for 30s, you want to capture the user input every 1s and perform an action.
