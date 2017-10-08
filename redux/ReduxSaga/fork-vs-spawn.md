## Fork vs spawn

```fork``` is an attached fork, while ```spawn``` is a detached fork. One explanation is to see the the saga hierarchy as a graph. ```fork``` creates a child from the calling process, while ```spawn``` creates a new child from the root.

When you create ```fork```, the parent process will wait until the ```fork``` process is finished. It means that every exception will bubble up from the ```fork``` -child- to the parent, so you can catch errors in the parent.

A spawned process won't block the parent, the next ```yield``` is called immediately. Thus the parent process won't be able to catch the exceptions from the spawned process.
