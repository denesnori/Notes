## Promises
Def: an object that might return a single value in the future
- either a resolved value
- or an error message why it is not resolved
- accept callbacks to be performed on the result or the reason for rejection
3 states:
- fulfilled
- rejected
- pending

```
fetch(url)
  .then(process)
  .then(save)
  .catch(handleErrors)
```

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
[Eric Elliott - Promises](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
[whatwg Fetch standard](https://fetch.spec.whatwg.org/)
(Promise it won't hurt workshop)[https://github.com/stevekane/promise-it-wont-hurt]
