# Float 浮动

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
.poem:first-letter {
  float: left;
  font-size: 54px;
  margin-right: 12px;
}
```
**运行结果** https://codepen.io/twhy/pen/mwPbRa

## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats
