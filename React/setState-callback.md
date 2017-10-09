## When to use React setState callback

```setState``` works in an asynchronous way. Which implies that the ```this.state``` variable is not immediately updated. If you want to perform an action immmediately after ```setState``` , which action relies on the current ```this.state``` , then you should use a callback.

### Example 1

Without a callback:
```
changeColor(event){
  this.setState({color:event.target.value});
  this.isItBlue();
}

isItBlue(){
  if (this.state.color==="blue"){
    return true;
  }
  return false;
}
```
Might not work as expected, there is a chance that the ```color``` variable might not have been updated before checking its value.

With a callback:
```
changeColor (event){
  this.setState({color:'blue'},this.isItBlue())
}

isItBlue(){
  if (this.state.color==="blue"){
    return true;
  }
  return false;
}
```


### Example 2: API call (preferably put it in Sagas)

```
changeSomething (event) {
  this.setState({someProp: event.target.value}, ()=> this.APICall())
}

APICall(){
  // call the API based on the updated state
}
```

### References
1. (React docs)[https://reactjs.org/docs/react-component.html#setstate]
