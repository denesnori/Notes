### lock files

yarn: yarn.lock
npm: package-lock.js

- automatically generated for every operation that modifies either the package.json or the node_modules.

- should be pushed to git.
Purpose:
- describes the exact tree that was generated, so teammates will install identical trees.
- time-travel to previous states of the node_modules
- optimize installation, ski repeated installs
