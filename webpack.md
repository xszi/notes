## webpack

### webpack 的发展

面向过程 ——> 面向对象 ——> 多个js文件（增加http请求）/ 代码不容易维护 ——> JS翻译器（webpack雏形）

### 定义

webpack是一个模块打包工具 —— bundler

JS 模块打包工具 ——> CSS, PNG等各种模块打包工具

阅读文档：

* concepts ——> Module
* Modules ——> API
* Guide ——> Get Started

### 打包配置 / 输出内容

```js
// webpack.config.js
module.exports = {
    // entry: 'index.js',
    entry: {
        main: 'index.js'
    },
    output: path.resolve(__dirname, 'bundle')
}
```


