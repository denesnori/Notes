## if

General
```
if [ conditions ]; then
  statement1
  statement2
fi
```


```
#!/bin/bash
if [-d $1]; then
  echo 'foo'
else
  echo 'bar'
fi
```
The above print foo when called without arguments.
Reason: test returns false if the argument is ```null``` and true otherwise.

```
[ -d ] && echo 'yes' // yes
[ -d '' ] && echo 'yes' // nothing
[ -f ] && echo 'yes' // yes
```
solution: quote ```$```, so that ```-d``` always gets an argument.
```
if [ -d '$1' ]; then
  echo 'foo'
else
  echo 'bar'
fi
```
