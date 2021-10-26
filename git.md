## 常用git命令

### git reset

```
git reset --soft commit_id // commit_id为提交hash值, 保留commit暂存的修改
git reset --hard commit_id // commit_id为提交hash值，不保留commit暂存的修改，慎重使用
```
**注意：**假如使用`git reset --hard`命令删除了之前的修改记录，补救办法有：使用`git reflog` 命令查找上一次提交的`commit hash`, 再次使用`git reset --hard hash`可以恢复原来的修改。