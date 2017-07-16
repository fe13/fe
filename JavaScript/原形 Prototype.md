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
🤔 那如果 `fan` 是 `String` / `Array` / `Function` 呢？

## Object.create()
`Object.create()` `ES5` 方法允许使用指定的原型对象和属性创建了一个新对象。
```javascript
// 常人的属性和方法
const personProto = {
  name: '',
  eat() { return '吃饭 🍚'; },
  sleep() { return '睡觉 😴'; },
  sing() { return '唱歌 🎤'; },
  intro() { return `大家好！我是${this.name}。`; },
};

// 让 personProto 作为 fan 的原形
let fan = Object.create(personProto);
fan.name = '吕粉丝';
fan.height = 162;
fan.gender = '女';
fan.travel = function() { return '环游世界 🌏🌎🌍'; }
```
显然，以下表达式都会返回 `true`。
```javascript
> fan.__proto__ === personProto
→ true

> personProto.isPrototypeOf(fan)
→ true

> personProto === Object.getPrototypeOf(fan)
→ true 
```
通过 `Object.keys()` 获取 `fan` 的所有属性名。
```javascript
> Object.keys(fan)
→ ["name", "height", "gender", "travel"]
```

## Object.prototype.hasOwnProperty()
`Object.prototype.hasOwnProperty()` 方法用于判定某个指定的属性是否对象的自身(非继承)属性。
```javascript
> for (let key in fan) console.log(key, fan[key])
  name 吕粉丝
  height 162
  gender 女
  travel function () { return '环游世界 🌏🌎🌍'; }
  eat function eat() { return '吃饭 🍚'; }
  sleep function sleep() { return '睡觉 😴'; }
  sing function sing() { return '唱歌 🎤'; }
  intro function intro() { return `大家好！我是${this.name}。`; }
→ undefined
```
由于 `for...in` 会把继承的属性和方法都进行遍历，因此需要 `Object.prototype.hasOwnProperty()`。
```javascript
> for (let key in fan) fan.hasOwnProperty(key) && console.log(key, fan[key])
  吕粉丝
  height 162
  gender 女
  travel function () { return '环游世界 🌏🌎🌍'; }
→ false
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

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty
