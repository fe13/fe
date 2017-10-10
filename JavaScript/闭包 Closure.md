# 闭包 Closure

> A closure is the combination of a function and the lexical environment within which that function was declared.

```javascript
function lastName(val) {
  return function(name) {
    return name.startsWith(val);
  };
}

[].find(lastName('王'))
[].find(lastName('李'))
```

```javascript
function assignTask(name) {
  var task = { id: 0, name };
  return function(person) {
    console.log(`${person} 执行任务 ${task.id} ${task.name}`);
  };
}
```

## 词法作用域 Lexical Scope

## Currying

## Coursera 课程
* [华盛顿大学 Programming Languages, Part A](https://www.coursera.org/learn/programming-languages)

## 参考链接
* https://javascript.info/closure
* https://en.wikipedia.org/wiki/Haskell_Curry
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures
