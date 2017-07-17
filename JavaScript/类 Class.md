# 类 Class

## 面向对象编程
面向对象编程(Object-oriented programming)，简称 OOP。OOP 简单来说就是用对象对现实世界进行建模进而解决问题。

## 构造器函数
JavaScrip 提供了构造函数用于构造对象。💡 构造函数名一般以大写开头(通常是名词)，方便与普通函数区分。
```javascript
function Person(name, gender, height) {
  this.name = name;
  this.gender = gender;
  this.height = height;
}

Person.prototype.intro = function() {
  return `大家好，我是${this.name}。`;
};

Person.prototype.sing = function(song) {
  return `唱一首 ${song} 🎤`;
}
```

## 继承
```javascript
function Artist(name, gender, height) {
  Person.call(this, name, gender, height);
}

Artist.prototype = Object.create(Person.proto);
Artist.prototype.constructor = Artist;

Artist.prototype.sing = function() {
  return ``;
};
```

## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target

