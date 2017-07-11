# 提升 Hoisting

JavaScript 中的提升(Hoisting)特指使用 `var` 声明的变量和函数声明被提升到所在作用域的顶端。

## 作用域 Scope
### 全局作用域 Global Scope
所有函数外的顶层环境被称为全局作用域，定义在全局作用域的值可以在任何地方被访问。
```javascript
var lyrics = '哟哟！';

function qkn() {
  lyrics += '切';
  return kn();
  
  function kn() {
    lyrics += '克';
    return nao();
    
    function nao() {
      lyrics += '闹！';
      return lyrics;
    }
  }
}
```
```javascript
> qkn()
→ 哟哟！切克闹！
```

### 函数作用域 Function Scope

### 块作用域 Block Scope

## 变量提升

## 函数提升

⚠️ 函数表达式不会被提升。

## 参考链接
* https://zhuanlan.zhihu.com/p/27558914
* https://github.com/getify/You-Dont-Know-JS/issues/767
* https://developer.mozilla.org/en-US/docs/Glossary/Hoisting
* http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html
* https://rainsoft.io/variables-lifecycle-and-why-let-is-not-hoisted
* http://adripofjavascript.com/blog/drips/variable-and-function-hoisting
* https://stackoverflow.com/questions/31219420/are-variables-declared-with-let-or-const-not-hoisted-in-es6
* https://medium.freecodecamp.org/what-is-variable-hoisting-differentiating-between-var-let-and-const-in-es6-f1a70bb43d

