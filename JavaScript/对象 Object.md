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

⚠️ `hannah.children` 是对 `babies` 数组的**引用**(Reference)，因此以下代码会直接修改 `babies`。
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
```javascript
let 专辑列表 = {
  周杰伦: {
    year: 2000,
    songs: [
      '可爱女人', '完美主义', '星晴', '娘子', '斗牛', '黑色幽默', 
      '伊斯坦堡', '印地安老斑鸠', '龙卷风', '反方向的钟'
    ],
  },
  范特西: {
    year: 2001,
    songs: [
      '爱在西元前', '爸我回来了', '简单爱', '忍者', '开不了口', 
      '上海一九四三', '对不起', '威廉古堡', '双截棍', '安静'
    ]
  },
  八度空间: {
    year: 2002,
    songs: [
      '半兽人', '半岛铁盒', '暗号', '龙拳', '火车叨位去',
      '分裂', '爷爷泡的茶', '回到过去', '米兰的小铁匠', '最后的战役'
    ]
  },
  叶惠美: {
    year: 2003,
    songs: [
      '以父之名', '儒夫', '晴天', '三年二班', '东风破', '你听得到',
      '同一种调调', '她的睫毛', '爱情悬崖', '梯田', '双刀'
    ]
  },
  七里香: {
    year: 2004,
    songs: [
      '我的地盘', '七里香', '借口', '外婆', '将军',
      '搁浅', '乱舞春秋', '困兽之斗', '园游会', '止战之殇'
    ]
  },
  十一月的萧邦: {
    year: 2005,
    songs: [
      '夜曲', '蓝色风暴', '发如雪', '黑色毛衣', '四面楚歌', '枫', 
      '浪漫手机', '逆鳞', '麦芽糖', '珊瑚海', '漂移', '一路向北'
    ]
  },
  依然范特西: {
    year: 2006,
    songs: [
      '夜的第七章', '听妈妈的话', '千里之外', '本草纲目', '退后',
      '红模仿', '心雨', '白色风车', '迷迭香', '菊花台'
    ]
  }
};
```

## new Object()
```javascript
var wyf = new Object();
wyf.name = '吴亦凡';
wyf.gender = '男';
wyf.intro = function() {
  return `大家好，我是${this.name}。`
};

new Object({ name: '吴亦凡', gender: '男' })
```

## Object.create()
`ES5` IE9+

## 参考链接
* http://www.objectplayground.com
* https://www.douban.com/doulist/234050
* http://2ality.com/2015/08/object-literals-es5.html
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions
* https://github.com/getify/You-Dont-Know-JS/blob/master/this%20&%20object%20prototypes/README.md


