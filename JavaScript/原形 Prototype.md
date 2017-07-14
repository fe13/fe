# 原形 Prototype

JavaScript 是一门基于**原形**的语言，每个对象都有一个原形(对象)作为模板。通过原形这种机制，对象能从其他对象继承功能特性；这种继承机制与经典的面向对象编程语言不同。**原型链**工作原理，通过 `prototype` 属性向已有的构造器添加方法。

`__proto__` 属性

`Object.getPrototypeOf()`

`prototype` 属性

`Object.prototype`
`String.prototype`

`constructor` 属性
`[].constructor.name`

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain
