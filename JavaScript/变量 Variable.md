# 变量 Variable

变量是一块用于存储值的内存空间，变量的特别之处在于它的值可以被改变。

## 声明变量
声明变量同时赋值
```javascript
var name = '斯蒂芬·库里';
var number = 30;
```

先声明变量再赋值
```javascript
var name;  // → undefined
name = '斯蒂芬·库里';
```
```javascript
var name, number, position;
name = '斯蒂芬·库里';
number = 30;
position = '控球后卫';
```

更改变量的值
```javascript
var price = 1000;

price = 1500;         // price is 1500

price = price + 300;  // price is 1800

price += 200          // price is 2000

price = price * 0.5   // price is 1000

price *= 1.5          // price is 1500
```

基于变量 `price` 声明其他变量
```javascript
var currentPriceTitle = '目前的价格是人民币 ' + price + ' 元';

price *= 0.85;

var discountPriceTitle = `打折后的价格是人民币 ${price} 元`;
```


## 变量名
```javascript
var hero name       // ❌ 变量名不能包含空格
var 2b              // ❌ 变量名不能以数字开头
var product_price   // 🆗
var $container      // ✅ 
var _counter        // ✅
var observable$     // ✅ 
var firstName       // ✅ 💯
var isMobileSafari  // ✅ 💯
```

## 变量类型

## let
`ES6`

## const
`ES6`

## 变量提升

## 参考链接
* 🇨🇳 http://javascript.ruanyifeng.com/grammar/basic.html
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types
