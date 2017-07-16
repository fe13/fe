# 原形 Prototype

JavaScript 是一门基于**原形**的语言，每个对象都有一个原形(对象)作为模板。

通过原形这种机制，对象能从其他对象继承功能特性；这种继承机制与经典的面向对象编程语言不同。

## `__proto__`属性
每个对象都有一个 `__proto__` 属性用于继承功能特性，该属性不是标准的一部分，但却是**事实标准**。  

声明对象 `fan` 如下，当访问 `name` `traval()` 等自身具有的属性/方法时，会从对象自身获取；  
当访问 `valueOf()` `toString()` 等非自身属性/方法时，会从(也只能) `__proto__` 属性上获取。
```javascript
let fan = {
  name: '吕粉丝',
  height: 162,
  gender: '女',
  eat() { return '吃饭 🍚'; },
  sleep() { return '睡觉 😴'; },
  sing() { return '唱歌 🎤'; },
  intro() { return `大家好！我是${this.name}。`; },
  travel() { return '环游世界 🌏🌎🌍'; }
};
```
```javascript
> fan.name
→ "吕粉丝"

> fan.travel()
→ "环游世界 🌏🌎🌍"

> fan.valueOf()
→ Object {name: "吕粉丝", height: 162, gender: "女", eat: function, sleep: function…}
```
## Object.prototype
以下代码都描述了同一个事实：`Object.prototype`(引用的对象) 是 `fan` 的原形。
```javascript
> fan.__proto__ === Object.prototype     // fan.__proto__ 和 Object.prototype 引用同一对象
→ true

> Object.prototype.isPrototypeOf(fan)    // Object.prototype(引用的对象) 是 fan 的原形
→ true

> Object.prototype === Object.getPrototypeOf(fan)
→ true
```


```javascript
let jay = {
  name: '周杰伦',
  height: 175,
  gender: '男',
  eat() { return '吃饭 🍚'; },
  sleep() { return '睡觉 😴'; },
  sing() { return '唱歌 🎤🎧🎸'; },
  aiyo() { return '哎哟，不错哦！'; }
}

let kris = {
  name: '吴亦凡',
  height: 187,
  eat() { return '吃饭 🍚'; },
  sleep() { return '睡觉 😴'; },
  sing() { return '唱歌 🎤🎧🎸'; },
  intro() { return `歌手${this.name}。其实我是一个演员。`; },
  ['有 freestyle 吗？']() {
    return ['有 freestyle 吗？', '还有 freestyle 吗？', '有没有 freestyle？'][Math.floor(Math.random() * 3)];
  }
}
```


`Object.getPrototypeOf()`

`constructor` 属性
`[].constructor.name`

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain
