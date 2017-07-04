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
