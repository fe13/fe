# 条件 Condition

> 人生或许没有如果，但是程序有。 --- 汤姆·尼古拉斯

## if
```javascript
// 通过 document.body.scrollTop 获取页面滚动距离
if (document.body.scrollTop > 0) {
  document.body.scrollTop = 0;
}
```

## if...else
```javascript
// Math.random() 用于生成一个 0 - 1 之间的随机数。
var a = Math.random();
var b = Math.random();
if (a > b) {
  console.log('随机数 a 大于 b');
} else {
  console.log('随机数 a 小于或等于 b');
}
```

## else if
```javascript
var width = window.innerWidth;  // 获取当前窗口宽度

if (width <= 320) {
  // ...
} else if (width > 320 && width < 768) {
  // ...
} else if (width >= 768 && width <= 1024) {
  // ...
} else {
  // ...
}
```

## switch


## ?:


## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else
