# 原形 Prototype

JavaScript 是一门基于**原形**的语言，每个对象都有一个原形(对象)作为模板。

通过原形这种机制，对象能从其他对象继承功能特性；这种继承机制与经典的面向对象编程语言不同。

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


`__proto__` 属性

`Object.getPrototypeOf()`

`prototype` 属性

`Object.prototype`
`String.prototype`

`constructor` 属性
`[].constructor.name`

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain
