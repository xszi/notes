### eslint的常用配置

*　函数名后面加空格

```json
// User ——> setting.json 中添加如下配置
 "javascript.format.insertSpaceBeforeFunctionParenthesis": true,
```

### 解决eslint与prettier格式化的冲突

```json
// .prettierrc
{
    "singleQuote": true,
    "semi": false
}
```

### vscode格式化配置与Eslint的格式配置冲突，可将vscode中的配置全部删除

设置 ——> 命令面板 ——> User/settings.json