# 循环

## while
`while` 在条件表达式为**真**的情况下循环执行一段代码，条件表达式会在代码块被执行前求值。

输出从 1 到 10
```javascript
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
输出从 1 到 10
```javascript
for (var i = 1; i <= 10; i++) {
  console.log(i);
}
```

输出从 10 到 1
```javascript
for (var i = 10; i > 0; i--) {
  console.log(i);
}
```

使用两个 `for` 输出 9 x 9 乘法表
```javascript
for (var i = 1; i < 10; i++) {
  for (var j = 1; j < 10; j++) {
    console.log(`${i} x ${j} = ${i * j}`);
  }
}
```

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while
