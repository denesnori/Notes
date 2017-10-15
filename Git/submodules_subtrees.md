## Submodules vs subtrees

### Submodule
- the main repo and the submodule act as independent repos.
- it is a link(reference) to the repo --> the size of the main repo won't increase
- If you push to a remote from the main repo, it doesn't push submodule files. If you need to change something in the submodule, you have to make a commit,push within the submodule.
- it is good for component based development. When the main repo depends on fixed version of another repository.
- you can make a submodule to follow the HEAD of a branch

```
git submodule add -b <branch> <repository> <path>
git submodule update --remote
```
## How git stores info on the submodules
1. .gitmodules file
- it is checked into the git repo -> changes is to this file are propagated to the collaborators.

2. .git/config
- it is the file that git checks when executing most commands.

#### Cloning a project with submodules

1. Clone the main repo
```
git clone https://github.com/your-repo
```

2.  Your submodule is ```mySubmodule```. If you list the files in the folder (```ls -la```), ```mySubmodule``` is there, but it is empty.
Run the following 2 commands:
```
git submodule init
````
 It initializes your local config file.

 ```
 git submodule update
 ```
 Fetch all the data from the submodule, and checkout the commit referred in your project.
#### Update submodules

```
#!/bin/bash
git pull '$@' &&
    git submodule sync --recursive &&
    git submodule update --init --recursive
```

##### Remove git submodules
//TODO unfinished



##### Explanation

```
git submodule sync
```
- compies the configuration from .gitmodules to .git/config.
- situation: Your submodule "example" is checkout from a URL. At one point the URL changes, from now on the submodules should be checked out from a different file. When you update the repo the ```.gitmodules``` file is updated, but not the ```.git/config```, it would still use the old path. --> run ```git submodule sync``` to update the URL in ```.git/config```.


```
git submodule update --init recursive
```
The submodule update command will recurse into the registered submodules, update and  init them - if required - and any nested submodules within.

#### Remove submodules
1. Remove the relevant section of the ```.gitmodules``` file.
2. stage  the changes
3. delete the relevant section form the ```.git/config``` file
4. run the command below
```
git rm --cached path-to-submodule
```
5. rm  
```
rm -rf .git/module/path-to-submodule
```
6. git commit -m 'remove submodule'
7. delete the now untracked submodule files
```
rm -rf path-to-submodules
```

```
git rm --cached path-to-file
```
- completely removes the file's contents from the index.
- on commit the file will be removed from the HEAD.

```
git reset --<path-to-file>
```
- reset the file in the index to be the same as the HEAD commit. --> no changes will be committed to this file
- it won't work if there is no version of the file in the HEAD commit.

## Subtree
- it is a copy. It is for code and history reuse. --> the size of the main repo increases after adding a subtree.
- If you push from the main repo to a remote, is pushes the subtree files.
- after integration there is no connection to the other repo, you only need to access it if you want to update it.


## other

list everything in the index under that folder
```
git ls-files --stage project folder
```

```git submodule init``` => only considers submodules that are already in the index (staged for initialization).
-> write a script that parses the submodules and run ```git submodule add <url> <path>```

```
git config -f path_to_a_config
```
use the given config file instead of the one in .git/config
