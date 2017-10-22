### functional programming

- creates programes by composing functions, avoids shared state and mutable data.
- Lisp (1958) was the first functional programming language, inspired by lambda calculus

- pure functions
- avoid side-effects
- function composition
- functional languages: Lisp, Haskell, Erlang, Clojure, Elm
- features in JS that support functional programming:
  - first-class functions
  - higher-order functions
  - functions as arguments, values

  ### Pure functions

  - given the same input, always return the same output
  - produces no side-effects
  - relies on no external mutable state
  - simplest reusable building blocks
  - a dead giveaway that a function is impure, that you call the function without using its return value. That can never happen with pure functions.

### Immutability
- object arguments are references --> if the function mutates an object or array parameter, that would mutate a state that is accessible outside the function.

### References
- (What is a pure function)[https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-pure-function-d1c076bec976]
