# 函数 Function

函数是一小段可重用的代码，可用于封装操作，计算结果并返回。函数最有趣的地方在于：它可以调用它自身，即**递归**。

## 声明函数
💡 勾股定理：平面上的直角三角形的两条直角边的长度（古称勾长、股长）的平方和等于斜边长（古称弦长）。  

一个用于计算直角三角形斜边长的函数
```javascript
function xc(a, b) {
  var a2 = a * a;
  var b2 = b * b;
  return Math.sqrt(a2 + b2);  // Math.sqrt() 用于开平方
}
```

## 调用函数
```javascript
> xc(3, 4)
→ 5

> xc(6, 8)
→ 10
```

## 匿名函数

## IIFE
IIFE 全称 Immediately-Invoked Function Expression，译作**立即执行の函数表达式**。
```javascript
(function() {
  console.log('立即执行🚀');
})();
```

## 函数 vs 方法

## 内置函数
* `alert()`
* `confirm()`
* `prompt()` `var guess = prompt('猜一个数字');`
* `console.log()`

## 作用域
### 全局作用域

### 局部作用域

## 箭头函数 Arrow Function
`ES6`

## 课后练习
```javascript
/**
 * 计算在某段文本 content 中出现某个字符串 search 的次数。
 * @param {string} content - 被搜索的文本内容
 * @param {string} search - 查找的字符串
 * @return {number} 字符串 search 在 content 中出现的次数，没有则返回 0。
 */
function appearances(content, search) {
  
} 
```

## 参考链接
* [勾股定理](https://zh.wikipedia.org/wiki/%E5%8B%BE%E8%82%A1%E5%AE%9A%E7%90%86)
* https://en.wikipedia.org/wiki/Pythagorean_theorem
* https://en.wikipedia.org/wiki/Immediately-invoked_function_expression
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters
