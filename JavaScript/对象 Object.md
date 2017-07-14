# 对象 Object

对象是一些相互关联的数据和功能(通常由若干变量和函数组成，被称为对象的属性和方法)的集合。

💡 在某些场合特指恋爱的对方。

## 声明对象
最常见的声明对象的方式是对象字面量，即使用 `{}` 声明。
```javascript
let babies = [
  { name: '周小凌', gender: '女' }
];

let jay = {
  name: '周杰伦',
  height: 175,
  children: babies,
  songs: ['星晴', '双节棍', '七里香', '简单爱', '青花瓷', '告白气球'],
  company: { name: '杰威尔音乐有限公司', location: '台北' },
  aiyo() {  // ES6
    return '哎哟，不错哦！';
  },
  intro: function() {
    return `大家好，我是${this.name}。`;
  }
};

let hannah = {
  name: '昆凌',
  height: 165,
  children: babies,
  catwalk() {
    return '👠👠👠👠👠👠👠👠👠';
  },
  intro: function() {
    return `大家好，我是${this.name}。`;
  },
  birth: function(name, gender) {
    if (this.children.find(child => child.name === name)) return;
    this.children.push({ name: name, gender: gender });
  }
};
```

## 访问对象
通过 `.` 访问
```javascript
> jay.name
→ "周杰伦"

> jay.company.name
→ "杰威尔音乐有限公司"

> jay.songs
→ ["星晴", "双节棍", "七里香", "简单爱", "青花瓷", "告白气球"]

> jay.aiyo()
→ 哎哟，不错哦！

> hannah.height
→ 165

> hannah.children
→ [{ name: "周小凌", gender: "女" }]

> hannah.children[0].name
→ "周小凌"

> hannah.catwalk()
→ 👠👠👠👠👠👠👠👠👠
```

通过 `[]` 访问
```javascript
> jay['name']
→ "周杰伦"

> jay['company']['location']
→ "台北"

> jay['intro']()
→ 大家好，我是周杰伦。
```

## 修改对象
```javascript
> jay.height = 198   // 修改身高 height 为 198
→ 198

> jay.height -= 23   // 修改身高 height 回 175
→ 175

> jay.wife = hannah;
→ Object {name: "昆凌", height: 165, children: Array(1), catwalk: function, intro: function…}

> jay.wife.name
→ "昆凌"

> hannah['husband'] = jay;
→ Object {name: "周杰伦", children: Array(1), songs: Array(6), company: Object, aiyo: function…}

> hannah['husband'].name
→ "周杰伦"
```

⚠️ `hannah.children` 是对 `babies` 数组的**引用**，因此以下代码会直接修改 `babies`。
```javascript
> hannah.children[0].name = 'Hathaway'
→ "Hathaway"

> babies[0]
→ Object { name: "Hathaway", gender: "女" }

> hannah.children.push({ name: '周小伦', gender: '男' })
→ 2

> babies
→ [{ name: "Hathaway", gender: "女" }, { name: "周小伦", gender: "男" }]

> jay.children.length
→ 2
```
以上 `hannah.children.push()` 操作其实在 `hannan.birth()` 已经实现了，因此可以写成
```javascript
hannah.birth('周小伦', '男');
```

### delete
`delete` 可用于删除对象的属性和方法。
```javascript
> delete jay.songs
→ true

> jay.songs
→ undefined

> delete hannah.catwalk
→ true

> hannah.catwalk
→ undefined
```
💡 `delete` 操作总是返回 `true`，无论属性或方法是否存在。

## this
`this` 指当前对象，在以下例子中 `this` 就是 `jay`。
```javascript
let jay = {
  name: '周杰伦',
  // ...
  intro: function() {
    return `大家好，我是${this.name}。`;
  }
};  
```
而以下例子中的 `this` 就是 `hannah`。
```javascript
let hannah = {
  name: '昆凌',
  // ...
  intro: function() {
    return `大家好，我是${this.name}。`;
  }
};
```
让他们分别自我介绍吧。
```javascript
> jay.intro()
→ 大家好，我是周杰伦。

> hannah.intro()
→ 大家好，我是昆凌。
```

## 遍历对象
`for...in`


## new Object()

## 参考链接
* http://www.objectplayground.com
* http://2ality.com/2015/08/object-literals-es5.html
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions
* https://github.com/getify/You-Dont-Know-JS/blob/master/this%20&%20object%20prototypes/README.md


