## 正则表达式

### 第一章 字符匹配

#### 1.1 两种模糊匹配

* 横向模糊匹配

```js
var regex = /ab{2,5}c/g
var string = 'abc abbc abbbbc'
console.log(string.match(regex)); // ['abbc', 'abbbbc']
```
* 纵向模糊匹配
```js
var regex = /a[123]b/g // [123]表示字符组，但表示的是其中一个字符
var string = 'a0b a1b a2b a3b a4b'
console.log(string.match(regex)); // ['a1b', 'a2b', 'a3b']
```

#### 1.2 特殊表示

* 范围表示法： [123456abcdefGHIJKLM] -> [1-6a-fG-M]

* 特殊[a-z]， 表示小写字符中的任何一个字符，不能用来匹配'a'、'-'、'z'中任意一个字符，应该写成[-az]或[az-]或[a\-z]

* [^abc]: 求反，表示一个除a, b, c之外的任意一个字母

* 常见的简写形式：

| 字符组 | 具体含义 |
| --- | --- |
| \d | [0-9], 一个数字， digit |
| \D | [^0-9], 除数字外的任意字符 |
| \w | [0-9a-zA-Z]， 数字，大小写字母和下划线 word单词字符|
| \W | [^0-9a-zA-Z]， 非单词字符 |
| \s | [\t\v\n\r\f]， 空白符，包括空格，水平制表符，垂直制表符，换行符，回车符，换页符。 white space|
| \S | [^\t\v\n\r\f], 非空白符 |
| . | [^\n\r\u2028\u2029]。 通配符，表示几乎任意字符。 换行符，回车符，行分隔符和段分隔符除外。|