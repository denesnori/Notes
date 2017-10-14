## Bash commands

## dirname
- return the directory name part of the filename.
- the directory the bash script is located at can be retrieved using ```dirname $0```.
```
#!/bin/bash
DIRECTORY = `dirname $0`
echo: $DIRECTORY
```

## function syntax
```
#!/bin/bash
function e {
  echo $1
}
```

## make a file executable
```
chmod u+x filename
```

## rm flags
-f: force: never propmt before removing
-R: remove directories and their content recursively
