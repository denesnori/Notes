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

#### Update submodules

```
#!/bin/bash
git pull '$@' &&
    git submodule sync --recursive &&
    git submodule update --init --recursive
```
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

## Subtree
- it is a copy. It is for code and history reuse. --> the size of the main repo increases after adding a subtree.
- If you push from the main repo to a remote, is pushes the subtree files.
- after integration there is no connection to the other repo, you only need to access it if you want to update it.
