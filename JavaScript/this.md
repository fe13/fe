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
在浏览器中以**非严格模式**直接调用函数，`this` 的值是 `window`。
```javascript
function whatsThis() {
  return this;
}
```
```javascript
> whatsThis() === window
→ true
```
在浏览器中以**严格模式**直接调用时，`this` 的值是 `undefined`。
```javascript
"use strict";
function whatsThis() {
  return this;
}
```
```javascript
> whatsThis()
→ undefined

> whatsThis() === void 0   // void 0 的值是 undefined
→ true
```
以下代码中的 `intro()` 也是直接调用。
```javascript
let product = {
  title: '太阳能电筒 🔦',
  intro() {
    return `${this.title} 您值得拥有 😎`;
  }
};

let intro = product.intro;
```
```javascript
> intro()
→ "undefined 您值得拥有 😎"     // 在严格模式下会报错

> product.intro()
→ "太阳能电筒 🔦 您值得拥有 😎"   // 正常方法调用
```

### this 的值是动态的
```javascript
function intro(face = '😉') {
  return `大家好！我叫${this.name}，请大家多多指教。${face}`;
}

let hmm = {
  name: '韩梅梅',
  intro
};

let lll = {
  name: '李雷雷',
  intro
};
```
```javascript
> hmm.intro()
→ "大家好！我叫韩梅梅，请大家多多指教。😉"

> lll.intro('😜')
→ "大家好！我叫李雷雷，请大家多多指教。😜"
```

### Function.prototype.call()
`Function.prototype.call()` 方法用指定的 `this` 值和参数(**逐个传递**)调用函数。

在上述 `韩梅梅` 和 `李雷雷` 的例子中，可以通过 `call()` 调用，不必添加 `intro` 方法。
```javascript
function intro(face = '😉') {
  return `大家好！我叫${this.name}，请大家多多指教。${face}`;
}

let hmm = { name: '韩梅梅' };
let lll = { name: '李雷雷' };
```
```javascript
> intro.call(hmm)
→ "大家好！我叫韩梅梅，请大家多多指教。😉"

> intro.call(lll, '😜')
→ "大家好！我叫李雷雷，请大家多多指教。😜"
```
将数组方法作用在`类似数组`的对象上。
```javascript
[].slice.call(document.querySelectorAll('div'))         // 将 NodeList 转成 Array

[].slice.call(document.querySelectorAll('div'), 3, 9)   // 获取 NodeList 中某些元素
```

使用 `Function.prototype.call()` 简化类的定义。
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

由于 `typeof []` 返回 `"object"`，因此在没有 `Array.isArray()` 时使用以下代码判断某个值是否数组。
```javascript
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray
if (!Array.isArray) {
  Array.isArray = function(arg) {
    return Object.prototype.toString.call(arg) === '[object Array]';
  };
}
```

### Function.prototype.apply()
`Function.prototype.apply()` 方法用指定的 `this` 值和参数(**数组传递**)调用函数。

将一个数组的所有元素添加到指定数组的末尾。
```javascript
> var a = [1, 2, 3, 4, 5], b = [6, 7, 8, 9, 10];
→ undefined

> a.push.apply(a, b)
→ 10

> a 
→ [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
找出数字数组中的最大值/最小值。
```javascript
> Math.max.apply(null, [6, 3, 5, 7, 8, 4, 2])
→ 8

> Math.min.apply(null, [6, 3, 5, 7, 8, 4, 2])
→ 2
```
`Function.prototype.apply()` 结合 `arguments` 一起使用。
```javascript
function concert() {
  console.log(`${this.name}演唱会 正式开始`);
  console.log([].slice.call(arguments).join(' '));
  console.log(`${this.name}演唱会 正式结束`);
}

let mayday = {
  name: '五月天',
  sing() {
    concert.apply(this, arguments);
  }
};
```
```javascript
> mayday.sing('Do You Ever Shine?', '三个傻瓜', '你不是真正的快乐', '为爱而生', '知足')
  五月天演唱会 正式开始
  Do You Ever Shine? 三个傻瓜 你不是真正的快乐 为爱而生 知足
  五月天演唱会 正式结束
→ undefined
```

### Function.prototype.bind()
```javascript
let taylor = {
  name: 'Taylor Swift',

  schedule(song, time) {
    setTimeout(function() {
      this.sing(song);
    }, time * 1000);
  },

  sing(song) {
    return '${song} 🎸 - ${this.name}';
  }
};

taylor.schedule('You Belong With Me', 3);
```

## 本节练习
* 以下代码会输出什么？
```javascript
"use strict";
let robot = {
  id: 'XD007',
  work() { console.log(`${this.id} 正在运作`) },
  rest() { console.log(`${this.id} 正在休息`) }
};
```
```javascript
> (new Date().getHours() >= 20 ? robot.rest : robot.work)()
→
```
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
* https://javascript.info/object-methods
* https://hacks.mozilla.org/2015/06/es6-in-depth-arrow-functions
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply
