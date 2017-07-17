# 类 Class

## 面向对象编程
面向对象编程(Object-oriented programming)，简称 OOP。OOP 简单来说就是用对象对现实世界进行建模进而解决问题。

## 构造器函数
JavaScrip 提供了构造器函数用于构造对象。💡 构造函数名一般以大写开头(通常是名词)，方便与普通函数区分。
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
  return `我要唱 ${song} 🎤`;
}
```
使用 `new` 创建新对象
```javascript
> let eva = new Person('依嬅', '女', 168)
→ undefined

> eva.name
→ "依嬅"

> eva.sing('倔强')
→ "我要唱 倔强 🎤"
```

### class
`ES6` 提供了 `class` 用于简化类的声明。
```javascript
class Person {
  constructor(name, gender, height) {
    this.name = name;
    this.gender = gender;
    this.height = height;
  }
  
  intro() {
    return `大家好，我是${this.name}。`;
  }
  
  sing() {
    return `我要唱 ${song} 🎤`;
  }
}
```

## 继承
```javascript
function Artist(name, gender, height) {
  Person.call(this, name, gender, height);
}

Artist.prototype = Object.create(Person.prototype);
Artist.prototype.constructor = Artist;

Artist.prototype.sing = function() {
  return ``;
};
```
### extends

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target

