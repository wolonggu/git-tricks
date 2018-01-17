# list git branch, HEAD, author

```
git branch -a | xargs -L 1 bash -c 'echo "$1 `git log --pretty=format:"%H %an" $1^..$1`"' _
```
