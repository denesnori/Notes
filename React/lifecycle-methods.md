# React lifecycle methods

##### The React lifecycle
1. Initial, component creation phase
2. Updates - triggered by state and prop changes
3. Unmounting phase

## Initialization
1. getDefaultProps // or ComponentName.defaultProps ={...} with ES6
2. getInitialState // this.state ={...} ES6 inside constructor
3. componentWillMount
4. Render
5. componentDidMount

```getDefaultProps``` and ```getInitialState``` are only called once, when the component is rendered for the firs time.

1. default props
Used to define default properties

ES6 way:
```
export default class Demo extends React.Component{
  ...
}

Demo.defaultProps = {
  name: 'demo',
}
```
ES5:

```
var Demo = createReactClass({
  getDefaultProps: function () {
    return {
      name: 'Mary',
    }
  }
})
```


2. initial state

ES6:
```
export class default Demo extends React.Component{
  constructor( props ){
    super(props);
    this.state = {
      counter: 0,
    }
  }

}
```
ES5

```
var Demo = createReactClass({
  getInitialState: function (){
    return {
      counter: 0,
    };
  }
})
```

3. componentWillMount
Called before the render method.
Note: setting a new state in ```componentWillMount``` won't trigger a render.
** By definition the ```render``` function has to be pure!!!***
Neither props, nor states should be changed inside the render.

4. Render
returns the markup. Child/Children nodes, or null or false.

5. componentDidMount
- the DOM can be accessed from this method --> we can perform DOM manipulation or fetch data.
- all DOM interactions should happen here and not in the render


## State changes
1. shouldComponentUpdate
2. componentWillUpdate
3. Render
4. componentDidUpdate

1. shouldComponentUpdate
- it is never called on the initial ```render```.
- otherwise always called before ```render``` to decide  whether the new render is necessary or not.
- has access both to the current and the next state and props.
- boolean value must be returned.

```
shouldComponentUpdate: function( nextProps, nextState ) {
  // return a boolean value
  return true;
}
```

2. componentWillUpdate
- should be strictly used to prepare for an update not to trigger updates.
- state changes via ```this.setState()``` are not allowed.

```
componentWillUpdate: function (nextProps, nextState){
  // prepare for the next update
}
```
3. render

4. componentDidUpdate
- Similar to ```componentDidMount```.
- perform DOM operations

## Props changes
Any changes on the ```props``` object will also trigger the lifecycle, almost indentical to state changes.
1. componentWillReceiveProps
2. shouldComponentUpdate
3. componentWillUpdate
4. Redner
5. componentDidUpdate

1. componentWillReceiveProps
- when the props have changes, and it is not the initial ```render```.
- enables to update the ```state``` depending on the current and the next props, without triggering another rendering.
- note: there is no such thing in the state update lifecycle. Since a state change should never trigger prop changes.

```
componentWillReceiveProps: function(nextProps){
  this.setState({
    // setting the state
  })
}
```

## Unmounting
### componentWillUnmount
- is called before a component is removed from the DOM.
- good for cleanup operations. Eg. remove the eventlisteners that were defined in ```componentDidMount```.


### References

1. (busypeoples - Rect component lifecycle)[http://busypeoples.github.io/post/react-component-lifecycle/]
2. (React without ES6)[https://reactjs.org/docs/react-without-es6.html]
