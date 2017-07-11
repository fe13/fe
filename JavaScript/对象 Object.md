# 对象 Object

对象是一些相互关联的数据和功能(通常由若干变量和函数组成，被称为对象的属性和方法)的集合。

💡 在某些场合特指恋爱的对方。

## 声明对象
```javascript
let jay = {
  name: '周杰伦',
  birthday: new Date('1979-01-18'),
  songs: ['星晴', '双节棍', '七里香', '简单爱', '青花瓷', '告白气球'],
  company: { name: '杰威尔音乐有限公司', location: '台北' },
  aiyo() {
    console.log('哎哟，不错哦！');
  },
  sing: function(song) {
    console.log(this.songs.indexOf(song) > -1 ? `接下来的是 ${song}` : '暂不支持播放');
  },
  intro: function() {
    console.log(`大家好，我是${this.name}。`);
  }
};

let hannah = {
  name: '昆凌',
  birthday: new Date('1993-08-12'),
  catwalk: function() {
    console.log('👠👠👠👠👠👠👠👠👠');
  }
};
```

## 访问对象
`.`
```javascript
> jay.name
→ "周杰伦"

> jay.company.name
→ "杰威尔音乐有限公司"

> jay.aiyo()
  哎哟，不错哦！
→ undefined

> hannah.catwalk()
  👠👠👠👠👠👠👠👠👠
→ undefined
```

`[]`

## 修改对象
```javascript
> jay.wife = hannah;
→ Object {name: "昆凌", birthday: Thu Aug 12 1993 ... (CST), catwalk: ... }

> jay.wife.name
→ "昆凌"

> hannah.husband = jay;
→ Object {name: "周杰伦", birthday: Thu Jan 18 1979 ... (CST), songs: ... aiyo: ...}

> hannah.husband.name
→ "周杰伦"
```

### delete

## 遍历对象
`for...in`


## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
