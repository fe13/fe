# 类 Class

## 面向对象编程
面向对象编程(Object-oriented programming)，简称 OOP。OOP 简单来说就是用对象对现实世界进行建模进而解决问题。

## 构造函数
```javascript
function Person(name) {
  this.name = name;
  this.intro = function() {
    return `大家好，我是${this.name}。`;
  };
}
```

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target
