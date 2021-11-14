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

devTool

### devServer

    * watch
    * devServer
    * node中直接调用运行webpack

### HMR(热更新)

* hot
* hotOnly

### Babel(处理ES6)

* babel-loader
* presets
* polyfill

```json
// .babelrc
{
    presets: [
        [
            "@babel/preset-env", {
                target: {
                    chrome: '67'
                },
                useBuiltIns: 'usage'
            }
        ],
        "@babel/preset-react"
    ]
}
```

### 打包环境的区分 production / development

webpack-merge

### Code Splitting & Tree-Shaking

代码分割的两种方式：

1. 同步代码在webpack中配置；
2. 异步加载代码无需配置会自动打包出一个新的文件；

### optimization ——> splitChunksPlugin

splitChunksPlugin：

* async：提高性能（异步）
* all：方便缓存（包括同步）

### 懒加载 / chunk

### 代码使用率 ——> 异步加载

### CSS文件的代码分割

    * MiniCssExtractPlugin

### webpack和浏览器缓存（caching）

    * contenthash

### Shimming(垫片)

    * imports-loader
    * webpack.ProvidePlugin

### 环境变量


###　案列环节：

#### Library打包

* external
* library
* libraryTarget: 'umd'

#### PWA的打包配置

* service-worker (页面缓存)

#### Typescript的打包配置

#### 使用WebpackDevServer实现请求转发

charles fiddler
```js
devServer: {}
bypass
target
pathRewrite
path
historyApiFallback
```


#### Eslint 的打包配置

#### webpack性能优化

1. 跟上技术迭代（node，npm，yarn）
2. 尽可能少的使用loader， plugin
3. 文件设置别名
4. DllPlugin (重要，特别是对于大型项目)
5. 控制包文件大小
6. thread-loader, parallel-webpack, happypack 多进程打包
7. 合理使用sourceMap
8. 结合stats分析打包结果
9. 开发环境内存编译
10. 开发环境无用插件剔除

#### 多页面打包