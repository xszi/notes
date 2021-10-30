## webpack4 学习笔记

### webpack是什么？

* 发展
  
面向过程 ——> 面向对象 ——> 多个js文件（增加http请求）/ 代码不容易维护 ——> JS翻译器 / JS 模块打包工具（webpack雏形）

* 定义

webpack是一个包含各类功能的模块打包工具 —— bundler

* 阅读文档：

[概念 —— 模块](https://webpack.docschina.org/concepts/modules/)
[API —— Modules](https://webpack.docschina.org/api/module-methods/)
[指南 ——> 起步](https://webpack.docschina.org/guides/getting-started/)


### 什么是loader？

    * 图片
    * 样式

### 什么是plugins？

    * HtmlWebpackPlugin
    * CleanWebpackPlugin

### SourceMap

### devServer

    * watch
    * devServer
    * node中直接调用运行webpack

### HMR(热更新)

### Babel(处理ES6)