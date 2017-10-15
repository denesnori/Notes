## Bash commands
-  a successful command returns 0
- an unsuccessful command returns a non-zero value

#### ```set -e```
exit immediately, if a pipeline (command,several commands) return a non zero status

#### source
- executes the content of the file passed in as asrgument
- it has a synonym ```.```
``` . filename args``` === ```source filename args```

#### dirname
- return the directory name part of the filename.
- the directory the bash script is located at can be retrieved using ```dirname $0```.
```
#!/bin/bash
DIRECTORY = `dirname $0`
echo: $DIRECTORY
```

#### function syntax
```
#!/bin/bash
function e {
  echo $1
}
```

#### make a file executable
```
chmod u+x filename
```

#### rm flags
-f: force: never propmt before removing
-R: remove directories and their content recursively

#### read
``` read varname varname ``` reads words and assigns them to variables.
