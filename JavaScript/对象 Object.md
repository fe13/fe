# 对象 Object

对象是一些相互关联的数据和功能(通常由若干变量和函数组成，被称为对象的属性和方法)的集合。
```javascript
{
  属性名: 属性值
  方法名: 函数
}
```

💡 在某些场合特指恋爱的对方。

## 声明对象
最常见的声明对象的方式是对象字面量，即使用 `{}` 声明。

⚠️ 中文变量名仅在现代浏览器如 Chrome 上得到良好支持，大部分情况下建议使用英文变量名，但中文其实很酷 😎。

声明一个空对象
```javascript
let empty = {};

let 空对象 = {};    // 现代浏览器对中文变量名支持良好
```
声明一个具有属性的对象
```javascript
let stephen = { name: "周星驰", height: 174, '生肖': '虎' };   // 在旧式浏览器上使用中文属性名需要引号

const 周星驰 = { 名字: "周星驰", 身高: 174, 生肖: '虎' };        // 在现代浏览器上使用中文属性名引号可选

let 阿星 = { 职业: '小混混', '如 来 神 掌': '🖐🖐🖐🖐🖐' };       // 包含空格或特殊字符的属性名需要引号
```
声明一个对象数组(暂时只有一个对象)
```javascript
let babies = [{ name: { zh: '周小凌', en: 'Hathaway' }, gender: '女' }];

let 宝贝 = [{ 名字: { 中文: '周小凌', 英文: 'Hathaway' }, 性别: '女' }];
```
声明包含属性和方法的对象
```javascript
let jay = {
  name: { zh: '周杰伦', en: 'Jay' },
  height: 175,
  children: babies,
  songs: ['星晴', '双节棍', '七里香', '简单爱', '青花瓷', '告白气球'],
  company: { name: '杰威尔音乐有限公司', location: '台北', year: { founded: 2007 } },
  like() { // ES6 方法定义
    return '哎哟，不错哦！';
  },
  intro: function(lang = 'zh') {
    return lang === 'zh' ? `大家好，我是${this.name.zh}。` : `Hi, I'm ${this.name.en}.`;
  }
};

const 周杰伦 = {
  名字: { 中文: '周杰伦', 英文: 'Jay' },
  身高: 175,
  子女: 宝贝,
  作品: ['星晴', '双节棍', '七里香', '简单爱', '青花瓷', '告白气球'],
  公司: { 名字: '杰威尔音乐有限公司', 所在地: '台北', 创办年份: 2007 },
  点赞() { // ES6 方法定义
    return '哎哟，不错哦！';
  },
  自我介绍: function(语言 = '中文') {
    return 语言 === '中文' ? `大家好，我是${this.名字.中文}。` : `Hi, I'm ${this.名字.英文}.`;
  }
};
```
使用 `new Object()` 方式声明对象`不常用`，`new` 可选。
```javascript
let hannah = new Object();
hannah.name = { zh: '昆凌', en: 'Hannah' };
hannah.height = 165;
hannah.children = babies;
hannah.catwalk = function() {
  return '🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈';
};
hannah.birth = function(gender, name) {
  this.children.push({ gender, name });  // ES6 对象缩写
  // this.children.push({ gender: gender, name: name });
};

const 昆凌 = Object({
  名字: { 中文: '昆凌', 英文: 'Hannah' },
  身高: 165,
  子女: 宝贝,
  猫步() {
    return '🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈';
  },
  分娩: function(婴儿性别, 中英文名) {
    this.子女.push({ 性别: 婴儿性别, 名字: 中英文名 });
  },
  自我介绍: function(语言 = '中文') {
    return 语言 === '中文' ? `大家好，我是${this.名字.中文}。` : `Hi, I'm ${this.名字.英文}.`;
  }
});
```

## 访问对象
通过 `.` 访问对象的属性和方法。
```javascript
> empty.anything    // 访问不存在的属性返回 undefined
→ undefined

> jay.height   // 周杰伦.身高
→ 175

> jay.name.zh
→ "周杰伦"

> 周杰伦.名字.英文
→ "Jay"

> jay.company.name    // 周杰伦.公司.名字
→ "杰威尔音乐有限公司"

> jay.company.year.founded    // 周杰伦.公司.创办年份
→ 2007

> jay.songs[0]    // 周杰伦.作品[0]
→ "星晴"

> jay.like()   // 周杰伦.点赞()
→ 哎哟，不错哦！

> hannah.catwalk()    // 昆凌.猫步()
→ "🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈🐈"

> hannah.children[0].name.zh
→ "周小凌"

> 昆凌.子女[0].名字.英文
→ "Hathaway"
```

通过 `[]` 也可以访问对象的属性和方法，当属性名包含空格或特殊字符，或属性名是变量时，一般使用 `[]`。
```javascript
> jay['height']
→ 175

> jay['company']['location']    // 周杰伦['公司']['所在地']
→ "台北"

> jay['intro']()    // 周杰伦['自我介绍']()
→ "大家好，我是周杰伦。"

> 阿星['如 来 神 掌']
→ "🖐🖐🖐🖐🖐"

> ['name', 'height'].map(function(property) { return jay[property] });
→ [{ zh: '周杰伦', en: 'Jay' }, 175]

> jay[prompt('查看 jay 的哪个属性？', 'songs')]
```
`ES6` 提供了对象解构(Object Destructuring)的方式简化访问对象的多个属性。
```javascript
let { name, songs, height } = jay;
```
等价于
```javascript
let name = jay.name;
let songs = jay.songs;
let height = jay.height;
```

## 修改对象
```javascript
> jay.age = 38    // 周杰伦.年龄 = 38
→ 38

> jay.age -= 10    // 周杰伦.年龄 -= 18   
→ 20               // 回到过去

> jay.wife = hannah
→ {name: Object, height: 165, children: Array(1), catwalk: function, birth: function}

> 周杰伦.妻子 = 昆凌;
→ {名字: Object, 身高: 165, 子女: Array(1), 猫步: function, 分娩: function}

> hannah.husband = jay
→ {name: Object, height: 175, children: Array(1), songs: Array(6), company: Object}

> 昆凌.丈夫 = 周杰伦
→ {名字: Object, 身高: 175, 子女: Array(1), 作品: Array(6), 公司: Object}

> jay.wife.name.zh    // 周杰伦.妻子.名字.中文
→ "昆凌"

> hannah.husband.name.zh    // 昆凌.丈夫.名字.中文
→ "周杰伦"
```

⚠️ `hannah.children` 是对 `babies` 数组的**引用**(Reference)，因此以下代码会直接修改 `babies`。
```javascript
> hannah.children[0].name.zh = '小周周'
→ "小周周"

> babies[0]
→ { name: { zh: '小周周', en: 'Hathaway' }, gender: '女' }

> 昆凌.子女[0].名字.中文 = '小周周'
→ "小周周"

> 宝贝[0]
→ { 名字: { 中文: '小周周', 英文: 'Hathaway' }, 性别: '女' }

> hannah.children.push({ name: { zh: '周小伦', en: 'Jason' }, gender: '男' })
→ 2

> babies
→ [{ name: { zh: '小周周', en: 'Hathaway' }, gender: '女' }
   { name: { zh: '周小伦', en: 'Jason'    }, gender: '男' }]

> 昆凌.子女.push({ 名字: { 中文: '周小伦', 英文: 'Jason' }, 性别: '男' })
→ 2

> 宝贝
→ [{ 名字: { 中文: '小周周', 英文: 'Hathaway' }, 性别: '女' }
   { 名字: { 中文: '周小伦', 英文: 'Jason'    }, 性别: '男' }]

> jay.children.length    // 周杰伦.子女.length
→ 2
```
以上 `hannah.children.push()` 操作其实在 `hannah.birth()` 已经实现了，因此可以写成
```javascript
hannah.birth('男', { zh: '周小伦', en: 'Jason' });

昆凌.分娩('男', { 中文: '周小伦', 英文: 'Jason' });
```

### delete
`delete` 可用于删除对象的属性或方法。
```javascript
> delete jay.songs    // delete 周杰伦.作品
→ true

> jay.songs           // 周杰伦.作品
→ undefined

> delete hannah.catwalk    // delete 昆凌.猫步
→ true

> hannah.catwalk    // 昆凌.猫步
→ undefined
```
💡 `delete` 操作总是返回 `true`，无论属性或方法是否存在。

## this
`this` 指**当前对象**，因此 `jay.intro()` 里面的 `this` 就是 `jay`，`hannah.intro()` 里面的 `this` 就是 `hannah`。

让他们分别自我介绍吧。
```javascript
> jay.intro()    // 周杰伦.自我介绍()
→ 大家好，我是周杰伦。

> hannah.intro()    // 昆凌.自我介绍()
→ 大家好，我是昆凌。
```

## 遍历对象
通过 `for...in` 可以遍历对象的属性和方法。
```javascript
周杰伦.专辑 = {
  周杰伦: {
    发行年份: 2000,
    专辑曲目: [
      '可爱女人', '完美主义', '星晴', '娘子', '斗牛', '黑色幽默', 
      '伊斯坦堡', '印地安老斑鸠', '龙卷风', '反方向的钟'
    ],
  },
  范特西: {
    发行年份: 2001,
    专辑曲目: [
      '爱在西元前', '爸我回来了', '简单爱', '忍者', '开不了口', 
      '上海一九四三', '对不起', '威廉古堡', '双截棍', '安静'
    ]
  },
  八度空间: {
    发行年份: 2002,
    专辑曲目: [
      '半兽人', '半岛铁盒', '暗号', '龙拳', '火车叨位去',
      '分裂', '爷爷泡的茶', '回到过去', '米兰的小铁匠', '最后的战役'
    ]
  },
  叶惠美: {
    发行年份: 2003,
    专辑曲目: [
      '以父之名', '儒夫', '晴天', '三年二班', '东风破', '你听得到',
      '同一种调调', '她的睫毛', '爱情悬崖', '梯田', '双刀'
    ]
  },
  七里香: {
    发行年份: 2004,
    专辑曲目: [
      '我的地盘', '七里香', '借口', '外婆', '将军',
      '搁浅', '乱舞春秋', '困兽之斗', '园游会', '止战之殇'
    ]
  },
  十一月的萧邦: {
    发行年份: 2005,
    专辑曲目: [
      '夜曲', '蓝色风暴', '发如雪', '黑色毛衣', '四面楚歌', '枫', 
      '浪漫手机', '逆鳞', '麦芽糖', '珊瑚海', '漂移', '一路向北'
    ]
  },
  依然范特西: {
    发行年份: 2006,
    专辑曲目: [
      '夜的第七章', '听妈妈的话', '千里之外', '本草纲目', '退后',
      '红模仿', '心雨', '白色风车', '迷迭香', '菊花台'
    ]
  },
  我很忙: {
    发行年份: 2007,
    专辑曲目: [
      '牛仔很忙', '彩虹', '青花瓷', '阳光宅男', '蒲公英的约定',
      '无双', '我不配', '扯', '甜甜的', '最长的电影'
    ]
  },
  魔杰座: {
    发行年份: 2008,
    专辑曲目: [
      '龙战骑士', '给我一首歌的时间', '蛇舞', '花海', '魔术先生',
      '说好的幸福呢', '兰亭序', '流浪诗人', '时光机', '乔克叔叔', '稻香'
    ]
  },
  跨時代: {
    发行年份: 2010,
    专辑曲目: [
      '跨时代', '说了再见', '烟花易冷', '免费教学录影带', '好久不见', '雨下一整晚',
      '嘻哈空姐', '我落泪·情绪零碎', '爱的飞行日记', '自导自演', '超人不会飞'
    ]
  },
  惊叹号: {
    发行年份: 2011,
    专辑曲目: [
      '惊叹号', '迷魂曲', 'Mine Mine', '公主病', '你好吗', '疗伤烧肉粽',
      '琴伤', '水手怕水', '世界未末日', '皮影戏', '超跑女神'
    ]
  },
  十二新作: {
    发行年份: 2012,
    专辑曲目: [
      '四季列车', '手语', '公公偏头痛', '明明就', '傻笑', '比较大的大提琴',
      '爱你没差', '红尘客栈', '梦想启动', '大笨钟', '哪里都是你', '乌克丽丽'
    ]
  },
  "哎呦，不错哦": {
    发行年份: 2014,
    专辑曲目: [
      '阳明山', '窃爱', '算什么男人', '天涯过客', '怎么了', '一口气全念对',
      '我要夏天', '手写的从前', '鞋子特大号', '听爸爸的話', '美人鱼', '听见下雨的声音'
    ]
  },
  周杰伦的床边故事: {
    发行年份: 2016,
    专辑曲目: [
      '床边故事', '说走就走', '一点点', '前世情人', '英雄', '不该',
      '土耳其冰激凌', '告白气球', 'Now you See me', '爱情废柴'
    ]
  }
};
```

## 常用方法
`Object.keys()` `ES5`

`Object.create()` `ES5`

## 本节练习
* 将以下对象改成用对象字面量来声明，尝试访问和修改对象，调用其方法。
```javascript
const 吴亦凡 = new Object();

吴亦凡.名字 = {
  中文: '吴亦凡',
  英文: 'Kris'
};

吴亦凡.自我介绍 = function() {
  return `歌手${this.名字.中文}。其实我是一个演员。`;
};

吴亦凡['有 freestyle 吗？'] = function() {
  return ['有 freestyle 吗？', '还有 freestyle 吗？', '有没有 freestyle？'][Math.floor(Math.random() * 3)];
};
```
* 将以上对象改成用对象字面量来声明，变量名使用英文，属性名使用中/英文(具体名字自定)。
* 使用 `ES6` 提供的特性重写以下函数，使之更简短。
```javascript
function createUser(firstName, lastName) {
  let fullName = firstName + ' ' + lastName;
  return {
    firstName: firstName,
    lastName: lastName,
    fullName: fullName,
    intro: function() {
      return "Hi, I'm " + this.fullName + '.';
    }
  };
}
```

## 参考链接
* http://www.objectplayground.com
* https://www.douban.com/doulist/234050
* http://2ality.com/2015/08/object-literals-es5.html
* https://mathiasbynens.be/notes/javascript-identifiers
* https://mathiasbynens.be/notes/javascript-identifiers-es6
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer
* https://github.com/getify/You-Dont-Know-JS/blob/master/this%20&%20object%20prototypes/README.md


