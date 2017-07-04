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

基于变量声明其他变量
```javascript
var pointsPerGame = 25.3;  // 2016-2017 场均得分
var pointsPerGameInText = '2016-2017 赛季场均得分为 ' + pointsPerGame + ' 分';

var totalThreePointers = 324;  // 2016-2017 三分命中总数;
var totalThreePointersInText = `2016-2017 赛季命中三分球 ${totalThreePointers} 个`;

var curry = `${name}，${position}，球衣号码 ${number}。`;
```

通过 `.` 可以访问变量的属性，如 `length`
```javascript
var team = '金州勇士队';
team.length

// 获取字符串最后一个字符
team[team.length - 1]
team.charAt(team.length - 1)
```

## 更改变量
```javascript
var price = 1000;

price = 1500;         // price is 1500

price = price + 300;  // price is 1800

price += 200          // price is 2000

price = price * 0.5   // price is 1000

price *= 1.5          // price is 1500
```

通过 `++` 可以让变量自增 1，`--` 可以让变量自减 1。
```javascript
var count = 5;

count++;   // count is 6

count--;   // count is 5
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

## 数据类型
* 数字 Number
* 字符串 String
* 布尔 Boolean
* 对象 Object
* Null
* Undefined
* Symbol `ES6`

## let
`ES6`

## const
`ES6`

## 变量提升

## 参考链接
* 🇨🇳 http://javascript.ruanyifeng.com/grammar/basic.html
* http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types
