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

### References
[Eric Elliott - Promises](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
[whatwg Fetch standard](https://fetch.spec.whatwg.org/)
