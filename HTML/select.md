## select dropdown

```
<select>
  <option selected disabled value="somehting">...</option>
  <option value="anything">...</option>
</select>
```
- if none of the options have a ```selected``` atrribute the first option will be preselected.
- you can make options not selectable with the ```disabled``` keyword.

### sideNote
Selects in React components:
- the ```onChange``` event is triggered on the ```<select>``` element and not the ```<option>``` element.
```
<select
  onChange = { (e)=>{
      console.log(e.target.value);
    } }
>
  <option>...</option>
  <option>...</option>
</select>
```
