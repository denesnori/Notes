### Closure

*When a function has access to the parent scope, even after the parent function has returned.*

*a stateful function*
- a closure gives access to an outer function's scope from an inner function.
- in JS they are the primary mechanism for data privacy
- create a function inside another function and expose the function -> return it or pass it to another function

- commonly used in JS for: object data privacy, in event handlers and callback function, currying, and other functional programming patterns.

- 3 possible states:
  - fulfilled
  - rejected
  - pending: not yet fulfilled or rejected

- settled (anything but pending) promises are immutable
- native JS promises don't expose states --> it is a blackbox. Only the function that creates the promises knows about its status, or access resolve/reject

Rules:
- a promise is an object must provide a  ```.then()``` method. Signature:
```
promise.then(
  onFulfilled: func,
  onRejected: func,
)
```
- a pending promise ->evolve -> rejected or fulfilled
- a fulfilled or rejected promise is settled -> it can't transition to any other state anymore

### Promise chaining
```
fetch(url)
  .then(process)
  .then(save)
  .catch(handleErrors)
```

### Error handling
```
save()
  .then(
    handleSuccess,
    handleError
    )
```
```
save()
  .then(handleSuccess)
  .catch(handleError)
```

### References
(Medium - Eric Elliott - Closures)[https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36]
(Promise it won't hurt workshop)[https://github.com/stevekane/promise-it-wont-hurt]
