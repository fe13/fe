# 条件 Condition

> 人生或许没有如果，但是程序有。 --- 汤姆·尼古拉斯

## if
```javascript
// document.body.scrollTop 为页面滚动距离
if (document.body.scrollTop > 0) {
  document.body.scrollTop = 0;
}
```

```javascript
var price = 1000, discount = 0.8;
var isMember = true;

if (isMember) {
  price *= discount;
}

console.log(`价格：人民币 ${price} 元`);
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
  console.log('窗口宽度 <= 320px');
} else if (width > 320 && width < 768) {
  console.log('320px < 窗口宽度 < 768px');
} else if (width >= 768 && width <= 1024) {
  console.log('768px <= 窗口宽度 <= 1024px');
} else {
  console.log('窗口宽度 > 1024px');
}
```
🤔 给定一个整数，当它可以被 3 整除或被 5 整除或同时能被 3 和 5 整除时，输出相应提示信息。

## switch
```javascript
switch(province) {
   case '江苏省':
   case '浙江省':
   case '上海市':
     console.log('江浙沪包邮!');
     break;
   case '广东省':
   case '福建省':
     console.log('邮费：20元');
     break;
   case '西藏自治区':
   case '新疆自治区':
   case '内蒙古自治区':
     console.log('邮费: 30元');
     break;
   case '香港特别行政区':
   case '澳门特别行政区':
     console.log('邮费: 60元');
     break;
   default:
     console.log('邮费: 18元')
}
```

使用 `switch` 替代多个 `if`
```javascript
var width = window.innerWidth;

switch(true) {
  case width < 320:
    console.log('窗口宽度 <= 320px');
    break;
  case width > 320 && width < 768:
    console.log('320px < 窗口宽度 < 768px');
    break;
  case width >= 768 && width <= 1024:
    console.log('768px <= 窗口宽度 <= 1024px');
    break;
  default:
    console.log('窗口宽度 > 1024px');
}
```

## ? :
```javascript
var status = navigator.onLine ? '在线' : '离线';
```


## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator
