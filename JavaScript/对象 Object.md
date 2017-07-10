# 对象 Object

对象是一些相互关联的数据和功能(通常由若干变量和函数组成，被称为对象的属性和方法)的集合。

💡 在某些场合特指恋爱的对方。

## 声明对象
```javascript
let jay = {
  name: '周杰伦',
  birthday: new Date('1979-01-18'),
  songs: [],
  aiyo() {
    console.log('哎哟，不错哦！');
  },
  sing: function() {
  
  }
}
```

## 访问对象
`.`
```javascript
> jay.name
→ "周杰伦"

> jay.aiyo()
  哎哟，不错哦！
→ undefined
```

`[]`

## 修改对象

### delete

## 遍历对象
`for...in`


## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
