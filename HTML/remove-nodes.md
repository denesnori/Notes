#### Remove element by id

```
var elelment = document.getElementById('element-id');
element.parentNode.removeChild('element');
```
- you can't remove an object directly from the DOM. -> you have go to its parent and remove it from there.
