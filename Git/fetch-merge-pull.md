```
git fetch
```
- download all the recent changes from origin, BUT! it won't put it in the current checkout branch

- Checkout the particular file from the downloaded changes
```
git checkout origin/master  -- <path/to/file>
```

### git fetvh vs git pull

```git pull``` = ```git fetch``` + ```git merge```

```
git blame <path/to/file>
```
- list who has changed what in a particular file
