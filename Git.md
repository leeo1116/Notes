
### 1. Push code on feature branch to master branch
#### 1.1 On feature branch
```
git rebase master  # need to deal with conflicts
git checkout master
git merge --squash feature
git status
git push
```
