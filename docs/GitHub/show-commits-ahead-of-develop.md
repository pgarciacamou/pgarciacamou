### Showing all commits from master ahead of develop

```bash
git log --pretty=oneline --abbrev-commit develop..master > tmp.txt
# OR
git log --pretty=oneline --abbrev-commit develop..master
```

Notice that the branch ahead must be on the right side
