# this

大部分情况下，`this` 的值由函数调用的方式决定。`this` 不能被赋值。

## Function.prototype.call()


## Function.prototype.apply()
```javascript
var a = [1, 2, 3, 4, 5], b = [6, 7, 8, 9, 10];
a.push.apply(a, b);
```

## Function.prototype.bind()

## 参考链接
* http://2ality.com/2014/05/this.html
* https://hacks.mozilla.org/2015/06/es6-in-depth-arrow-functions
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this
