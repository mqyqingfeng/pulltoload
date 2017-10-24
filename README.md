# pulltoload

## 介绍

移动端上拉加载库，原生 JavaScript 实现。

效果演示：

[https://mqyqingfeng.github.io/pulltoload/](https://mqyqingfeng.github.io/pulltoload/)

[https://mqyqingfeng.github.io/pulltoload/second.html](https://mqyqingfeng.github.io/pulltoload/second.html)

## 相关

[下拉刷新库](https://github.com/mqyqingfeng/pulltorefresh)

## 依赖

原生 JavaScript 实现，无依赖。

## 大小

压缩后 3KB，gzip 压缩后更小。

## 下载

```js
git clone git@github.com:mqyqingfeng/pulltoload.git
```

## 使用

```html
<script src="path/pulltoload.js"></script>
```

或者

```js
import PullToLoad from 'path/pulltoload.js'
```

## 示例

```js
var pull = new PullToLoad("#main", {
    // 当滑动到距离底部还有 100px 的时候就触发加载事件
    threshold: 100,
    // 指定 loading 的 selector
    loader: '#loader'
})

// 绑定加载事件
pull.on("load", function(reset){
    setTimeout(function(){
        // 注意，当加载结束后，调用 reset 函数，以重置 loading
        reset()
    }, 1000)
})
```

## API

### 初始化

```js
var pulltoload = new PullToLoad(selector, options);
```

### options

**1.threshold**

默认值为 `100`，表示当滑动到距离底部还有 100px 的时候就触发加载事件。

**2.loader**

默认值为 `#loader`，表示加载时的 loading 的选择符。

注意: loading 需要用户自己定义，然后在这里传入该 loading 元素的选择符。

### 事件绑定

```js
pulltoload.on("load", function(reset) {
    // 模拟请求接口
    setTimeout(function() {
        // 注意，当加载结束后，调用 reset 函数，以重置 loading
        reset()
    }, 1000)
})
```
