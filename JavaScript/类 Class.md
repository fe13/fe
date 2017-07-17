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
};
```
使用 `new` 创建新对象。
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
  
  sing(song) {
    return `我要唱 ${song} 🎤`;
  }
}
```

## 继承
```javascript
function Artist(name, gender, height, agent) {
  Person.call(this, name, gender, height);
  this.agent = agent;
}

Artist.prototype = Object.create(Person.prototype);
Artist.prototype.constructor = Artist;    // 设置正确的 constructor 值

Artist.prototype.sing = function(song) {
  return `${song} 会唱的一起唱好吗 🎸`;
};
```
```javascript
> let ashin = new Artist('陈信宏', '男', 180, '相信音乐')
→ undefined

> ashin.name
→ "陈信宏"

> ashin.agent
→ "相信音乐"

> ashin.sing('恋爱ing')
→ "恋爱ing 会唱的一起唱好吗 🎸"
```

### extends

## 参考链接
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target

