## 常用git命令

### commit使用

1. 每做完一个功能需求，可以顺利跑起来，先使用commit提交到本地保存；
2. 修改或者优化重构功能时，完成跑测试，测试通过后再次通过commit提交到本地保存；
3. 如果后续再修改时，搞乱了，可以回滚到上次继续下去；
4. 推送到远端仓库前，把零碎的修改压缩成一个更有意义的提交。

### git reset

```
git reset --soft commit_id // commit_id为提交hash值, 保留commit暂存的修改
git reset --hard commit_id // commit_id为提交hash值，不保留commit暂存的修改，慎重使用
```
**注意：**假如使用`git reset --hard`命令删除了之前的修改记录，补救办法有：使用`git reflog` 命令查找上一次提交的`commit hash`, 再次使用`git reset --hard hash`可以恢复原来的修改。