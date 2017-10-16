### React refs

- in React parent coomponent normally interact with their children vis ```props``` -> rerender the children with new props.
- you can imperatively modify children with ```ref```s.
- the child to be updated can be a React component or a DOM element.

When you should use refs:
- focus, text selection, media playback
- trigger imperative animations
- 3rd-party DOM libraries

Avoid using refs for stuff that can be done declaratively.

## adding ```ref```s
- ```ref``` react attribute, can be attached to components ot DOM elements
- ```ref``` takes a callback function, which is executed immediately after the component is mounted/ unmounted
- the ```ref``` callback receives the underlying DOM node as its argument
- react calls the ```ref``` callback with the DOM node when the component mounts, and with ```null``` when it unmounts.

```
class Example extends React.Component{
  componentDidMount(){
    this.onFocus();
  }

  onFocus = () =>{
    this.textInput.focus();
  }

  render(){
    <div>
      <input
        type="text"
        ref = { (input) => this.textInput = input}
      />
    </div>
  }
}
```

### Adding ```ref``` to a class component

- ```ref``` on a non-function component, the ```ref``` callback receives the mounted component as its argument.
- only works if ```Demo``` is declared as a class!!!

```
class Demo extends React.Component{
  componentDidMount(){
    this.input.focusTextInput(;)
  }
  render(){
    return (
      <CustomTextInput
        ref={(input) => {
          this.input = input;
          }}
      />
      );
  }
}
```
#### Can't use ```ref```s on functional compoennts
You can't use ```ref```s on functional components since the don't have instances.
- convert the functional component to a class, so that you can access lifecycle methods
- or use ```ref```s inside functional components, and attach them to DOM nodes

### Exposing DOM refs to parent components

#### references
- (reactjs- Refs and the DOM)[https://reactjs.org/docs/refs-and-the-dom.html]
