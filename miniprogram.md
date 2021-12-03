## 微信小程序

### 开发注意

* 安装毒霸杀毒软件会导致微信开发者工具的调试panel打开为空白；

### 文档阅读记录

1. 页面可以引用 `behaviors` 。 `behaviors` 可以用来让多个页面有相同的数据字段和方法。
2. 通过全局函数 `getApp` 可以获取全局的应用实例，如果需要全局的数据可以在 `App()` 中设置，如：

```js
    // app.js
    App({
    globalData: 1
    })
```
3. 自定义组件

### 开发总结

#### 解决小程序Page页面不能使用observer监听数据变化

```js
// app.js
// 先在app.js中全局引入监听方法，使用defineProperty
App({
    onLaunch: function (e) {},
    // 全局监听方法
    watch: function (ctx, obj) {
        Object.keys(obj).forEach(key => {
            this.observer(ctx.data, key, ctx.data[key], function (value) {
                obj[key].call(ctx, value)
            })
        })
    },
    // 监听属性，并执行监听函数
    observer: function (data, key, val, fn) {
        Object.defineProperty(data, key, {
            configurable: true,
            enumerable: true,
            get: function () {
                return val
            },
            set: function (newVal) {
                if (newVal === val) return
                fn && fn(newVal)
                val = newVal
            }
        })
    }
})
```

```js
// xxx.js 某Page页面使用
const t = getApp()
Page({
    data: {
        test: ''
    },
    onLoad(options) {
        // 使用，可以监听test变化，触发相应的函数事件
        t.watch(this, {
            test: function(newVal) {
                console.log(newVal);
            }
        })
    }
})
```

#### 小程序使用WeUI组件库

* 通过useExtendedLib扩展引入weui （不占用小程序的包体积）

1、在app.json中配置
```js
"useExtendedLib": {
    "weui": true
}
```

2、在对应的文件的json引入你需要的组件
```js
"usingComponents": {
    "mp-loading": "weui-miniprogram/loading/loading"
},
```
3、在wxml文件使用组件
```html
<mp-loading></mp-loading>
```

* 通过npm包管理引入，不建议，会增加包的体积

#### 小程序嵌入H5，H5跳转小程序

小程序可以内嵌H5：

* 微信小程序通过web-view内嵌了h5后，无法使用微信支付，需使用小程序支付

h5可以跳转小程序，小程序回到H5必须要有按钮来操作


#### 小程序调用腾讯SDK进行视频录制和视频连线，websocket+PC

#### 小程序支付和公众号H5支付
