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
在函数内部时，`this` 的值取决于函数的调用方式。

### 直接调用
```javascript
function whatsThis() {
  
}
```

### Function.prototype.call()
`Function.prototype.call()` 方法用指定的 `this` 值和参数(**逐个传递**)调用函数。

使用 `call()` 简化类的定义。
```javascript
function Person(name, gender, height) {
  this.name = name;
  this.gender = gender;
  this.height = height;
}

(function() {

  this.intro = function() {
    return `大家好，我是${this.name}。`;
  };

  this.sing = function(song) {
    return `我要唱 ${song} 🎤`;
  };

  this.isTallerThan = function(person) {
    return person && person.height < this.height;
  };

}).call(Person.prototype);
```

### Function.prototype.apply()
`Function.prototype.apply()` 方法用指定的 `this` 值和参数(**数组传递**)调用函数。
```javascript
> Math.max.apply(null, [6, 3, 5, 7, 8, 4, 1])
→ 8
```

由于 `typeof []` 返回 `"object"`，因此在没有 `Array.isArray()` 时使用以下代码判断某个值是否数组。
```javascript
if (!Array.isArray) {
  Array.isArray = function(value) {
    return Object.prototype.toString.apply(value) === '[object Array]';
  };
}
```

### Function.prototype.bind()

## 本节练习
* 如何让 `kris` 说 "大家好！我是吴亦凡。" ？
```javascript
function intro() {
  return `大家好！我是${this.name}。`;
}

let kris {
  name: '吴亦凡',
  intro: function() { return `歌手${this.name}。其实我是一个演员。`; }
};
```


## 参考链接
* http://2ality.com/2014/05/this.html
* https://hacks.mozilla.org/2015/06/es6-in-depth-arrow-functions
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply
