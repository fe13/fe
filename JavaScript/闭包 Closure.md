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

## 参考链接
* https://javascript.info/closure
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures
