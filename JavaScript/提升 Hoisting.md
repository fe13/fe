# 提升 Hoisting

JavaScript 中的提升(Hoisting)特指使用 `var` 声明的变量和函数声明被提升到所在作用域的顶端。

## 变量提升
使用 `var` 声明的变量被提升到所在作用域的顶端，因此以下函数 `met()`
```javascript
function met() {
  lyrics = '听见 冬天的离开';
 
  console.log(lyrics);
 
  var lyrics;  // lyrics 被提升到作用域顶端
}
```
等同于
```javascript
function met() {
  var lyrics;
  
  lyrics = '听见 冬天的离开';
 
  console.log(lyrics);
}
```
💡 值得注意的是，**被提升的是声明，而不是赋值**。因此以下函数 `nodiff()`
```javascript
function nodiff() {
  console.log(lyrics);
  
  var lyrics = '因为我们没有什么不同';
}
```
等同于
```javascript
function nodiff() {
  var lyrics;  // 未赋值的变量值是 undefined
  
  console.log(lyrics);  // 输出 undefined
  
  lyrics = '因为我们没有什么不同';
}
```

⚠️ `let` 不存在变量提升。

## 函数提升
函数声明会被提升到所在作用域的顶端，因此调用语句可以放在函数声明之前。
```javascript
(function() {

  sing();
  
  function sing() {
    console.log('少林功夫好耶 真好耶🎸');
  }
  
})();
```
⚠️ 函数表达式不会被提升，因此调用前要先声明，否则会报错。
```javascript
(function() {
  
  var moon = function() { console.log('床前明月光，疑是地上霜。'); }
  
  moon();  // 正常
  home();  // 报错 Uncaught TypeError: home is not a function
  
  var home = function() { console.log('举头望明月，低头思故乡。'); }

})();
```

## 参考链接
* http://es6.ruanyifeng.com
* https://zhuanlan.zhihu.com/p/27558914
* https://github.com/getify/You-Dont-Know-JS/issues/767
* https://developer.mozilla.org/en-US/docs/Glossary/Hoisting
* http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html
* https://rainsoft.io/variables-lifecycle-and-why-let-is-not-hoisted
* http://adripofjavascript.com/blog/drips/variable-and-function-hoisting
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let
* https://stackoverflow.com/questions/31219420/are-variables-declared-with-let-or-const-not-hoisted-in-es6
* https://medium.freecodecamp.org/what-is-variable-hoisting-differentiating-between-var-let-and-const-in-es6-f1a70bb43d

