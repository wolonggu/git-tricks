# list git branch, HEAD, author

```
git branch -a | xargs -L 1 bash -c 'echo "$1 `git log --pretty=format:"%H %an" $1^..$1`"' _
```

# To delete all branches on remote that are already merged:

```
git branch -r --merged | grep -v master | sed 's/origin\//:/' | xargs -n 1 git push origin
```

In more recent versions of Git

```
git branch -r --merged | grep -v master | sed 's/origin\///' | xargs -n 1 git push --delete origin
```

# show authors of commit

```
git log --format='%ae' COMMIT_ID
```

or 

```
git show 1918e863e8f3d0f5f4e87c864555a27ba9c73f59 --stat | grep Author
```
