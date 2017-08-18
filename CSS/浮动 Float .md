# 浮动 Float

## 浮动的起源
`float` 属性最初被引入用来实现图片被文字围绕的效果，类似报纸中的一篇图文报道。
```html
<p class="poem">
  君不见，黄河之水天上来，奔流到海不复回。
  君不见，高堂明镜悲白发，朝如青丝暮成雪。
  人生得意须尽欢，莫使金樽空对月。
  天生我材必有用，千金散尽还复来。
  烹羊宰牛且为乐，会须一饮三百杯。
  岑夫子，丹丘生，将进酒，杯莫停。
  与君歌一曲，请君为我倾耳听。
  钟鼓馔玉不足贵，但愿长醉不复醒。
  古来圣贤皆寂寞，惟有饮者留其名。
  陈王昔时宴平乐，斗酒十千恣欢谑。
  主人何为言少钱，径须沽取对君酌。
  五花马，千金裘，呼儿将出换美酒，与尔同销万古愁。
</p>
```
```css
.poem::first-letter {
  float: left;
  font-size: 54px;
  margin-right: 12px;
}
```
**运行结果** https://codepen.io/twhy/pen/mwPbRa

## 多列布局
### 两列布局
```html
<h1>苏轼</h1>

<section class="left">
  <article>
    <h2>念奴娇·赤壁怀古</h2>
    <p>
      大江东去，浪淘尽，千古风流人物。
      故垒西边，人道是：三国周郎赤壁。
      乱石穿空，惊涛拍岸，卷起千堆雪。
      江山如画，一时多少豪杰。
    </p>
    <p>
      遥想公瑾当年，小乔初嫁了，雄姿英发。
      羽扇纶巾，谈笑间樯橹灰飞烟灭。
      故国神游，多情应笑我，早生华发。
      人生如梦，一尊还酹江月。 
    </p>
  </article>
</section>

<section class="right">
  <article>
    <h2>水调歌头·明月几时有</h2>
    <p>
      明月几时有，把酒问青天。
      不知天上宫阙，今夕是何年。
      我欲乘风归去，又恐琼楼玉宇，高处不胜寒。
      起舞弄清影，何似在人间？
    </p>
    <p>
      转朱阁，低绮[qǐ]户，照无眠。
      不应有恨，何事长向别时圆？
      人有悲欢离合，月有阴晴圆缺，此事古难全。
      但愿人长久，千里共婵娟。
    </p>
  </article>
</section>
```
```css
h1, h2 { 
  text-align: center;
}

.left, .right {
  width: 48%;
  margin: 0 1%;
}

.left { 
  float: left;
}

.right { 
  float: right;
}
```
**运行结果** https://codepen.io/twhy/pen/eRZmzw

### 三列布局
```html
<h1>杜甫</h1>

<section class="left">
  <article>
    <h2>望岳</h2>
    <p>岱宗夫如何？齐鲁青未了。</p>
    <p>造化钟神秀，阴阳割昏晓。</p>
    <p>荡胸生层云，决眦入归鸟。</p>
    <p>会当凌绝顶，一览众山小。</p>
  </article>
</section>

<section class="middle">
  <article>
    <h2>泊秦淮</h2>
    <p>烟笼寒水月笼沙，夜泊秦淮近酒家。</p>
    <p>商女不知亡国恨，隔江犹唱后庭花。</p>
  </article>
</section>

<section class="right">
  <article>
    <h2>春望</h2>
    <p>国破山河在，城春草木深。</p>
    <p>感时花溅泪，恨别鸟惊心。</p>
    <p>烽火连三月，家书抵万金。</p>
    <p>白头搔更短，浑欲不胜簪。</p>
  </article>
</section>
```
```css
h1, h2, article {
  text-align: center;
}

.left, .middle, .right {
  width: 31%;
  float: left;
  margin: 0 1%;
}
```
**运行结果** https://codepen.io/twhy/pen/YQqPEx

## 清除浮动
浮动会造成父容器高度坍塌，因此要清理浮动。
### `overflow: hidden`
```html
<div class="links">
  <a href="#" class="forget">忘了密码？</a>
  <a href="#" class="register">注册新账号</a>
</div>
```
```css
.links { overflow: hidden; }
.links .forget { float: left; }
.links .register { float: right; }
```

### `.clearfix`
将以下 `.clearfix` 类应用到需要清除浮动的父元素。
```css
.clearfix::after {
  content: '';
  clear: both;
  display: block;
}
```

## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats
* https://www.w3.org/TR/CSS21/visuren.html#block-formatting
* https://stackoverflow.com/questions/4910075/why-overflow-hidden-clears-a-float
* https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context
* https://stackoverflow.com/questions/211383/what-methods-of-clearfix-can-i-use
* https://css-tricks.com/snippets/css/clear-fix/
