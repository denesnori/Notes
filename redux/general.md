## Redux

- based on the Flux architecture/pattern
- state management tool.
- reducers:
  - ```oldState + action = newState```
  - responsible for updating the state.
  - must be pure functions  (implies that they can't have side effects, can't fire network requests)
- just a small number of components depend on Redux, the other components just receive state and callbacks as props

Flow:
1. components are given callback  functions as props, which they call when a specific event happens
2.  the callbacks create and dispatch actions
3. reducers process the actions, computing the new state
4. the new application state is stored in the store (single source of truth)
5. components receive the new state as props and rerender


### references
- (Flux architecture)[https://facebook.github.io/flux/]
- (camjackson)[https://camjackson.net/post/9-things-every-reactjs-beginner-should-know]
