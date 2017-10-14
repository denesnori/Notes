
\W: all non alpha-numeric chars, _ excluded
Eg.: remove all non alpha num chars

```
text.replace(/[\W_]+/g," ");
```
```[^a-zA-Z0-9]``` egquvalent to ```[\W_]```
