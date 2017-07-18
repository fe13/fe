# this

大部分情况下，`this` 的值由函数调用的方式决定。`this` 不能被赋值。

## 全局上下文 Global Context
在浏览器的全局环境中，`this` 的值是 `window`。
```javascript
> this === window
→ true

> this.dog = '🐶';
→ "🐶"

> window.dog
→ "🐶"
```

## 函数上下文 Function Context

### Function.prototype.call()
`Function.prototype.call()` 方法用指定的 `this` 值和参数(逐个传递)调用函数。

### Function.prototype.apply()
```javascript
var a = [1, 2, 3, 4, 5], b = [6, 7, 8, 9, 10];
a.push.apply(a, b);
```

### Function.prototype.bind()

## 本节练习
* 如何让 `kris.intro()` 返回 "大家好！我是吴亦凡。" ？
```javascript
const personProto = {
  name: '',
  sing() { return '唱歌 🎤'; },
  intro() { return `大家好！我是${this.name}。`; }
};

const artistProto = Object.create(personProto);
artistProto.sing = function() { return '唱歌 🎤🎧🎸'; };

let kris = Object.create(artistProto);
kris.name = '吴亦凡';
kris.intro = function() { return `歌手${this.name}。其实我是一个演员。`; };
```


## 参考链接
* http://2ality.com/2014/05/this.html
* https://hacks.mozilla.org/2015/06/es6-in-depth-arrow-functions
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply
