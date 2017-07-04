# 循环

## while
`while` 在条件表达式为**真**的情况下循环执行一段代码，条件表达式会在代码块被执行前求值。
```javascript
// 输出从 1 到 10
var n = 1;
while (n <= 10) {
  console.log(n);
  n += 1;
}
```

```javascript
while (true) {
  // 一直不断被执行的代码
}
```

```javascript
while (false) {
  // 永远不会被执行的代码
}
```

## for
```javascript
// 输出从 1 到 10
for (var i = 1; i <= 10; i++) {
  console.log(i);
}
```


## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while
