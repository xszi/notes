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