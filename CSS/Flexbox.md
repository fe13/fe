# Flexbox

Flexbox 为 CSS 提供了更强大的布局方式。

## display: flex
```html
<header>
  <h1>李商隐</h1>
</header>
<section>
  <article>
    <h2>锦瑟</h2>
    <p>锦瑟无端五十弦，</p>
    <p>一弦一柱思华年。</p>
    <p>庄生晓梦迷蝴蝶，</p>
    <p>望帝春心托杜鹃。</p>
    <p>沧海月明珠有泪，</p>
    <p>蓝田日暖玉生烟。</p>
    <p>此情可待成追忆，</p>
    <p>只是当时已惘然。</p>
  </article>
  <article>
    <h2>夜雨寄北</h2>
    <p>君问归期未有期，</p>
    <p>巴山夜雨涨秋池。</p>
    <p>何当共剪西窗烛，</p>
    <p>却话巴山夜雨时。</p>
  </article>
  <article>
    <h2>别薛喦宾</h2>
    <p>曙爽行将拂，晨清坐欲凌。</p>
    <p>别离真不那，风物正相仍。</p>
    <p>漫水任谁照，衰花浅自矜。</p>
    <p>还将两袖泪，同向一窗灯。</p>
    <p>桂树乖真隐，芸香是小惩。</p>
    <p>清规无以况，且用玉壶冰。</p>
  </article>
</section>
```
```css
body {
  text-align: center;
  background: #f8f8f8;
}

section {
  display: flex;  /* article 等高 */
}

section > article {
  flex: 1;  /* article 等宽 */
  margin: 10px;
  background: #fff;
  padding: 0 10px 15px;
  border-radius: 4px;
  border: 1px solid #ddd;
  box-shadow: 1px 1px 3px #ddd;
}
```
🚀 https://codepen.io/twhy/pen/MopwzL

💡 如果希望 flex 容器表现的像行内元素，可以设置 `display: inline-flex`。

### 常用术语
| 术语      | 英文            | 含义/解析                                         |
|----------|-----------------|--------------------------------------------------|
| flex 容器 |  flex container | `display: flex` 或 `display: inline-flex` 的元素  |
| flex 子项 |  flex items     | flex 容器中的子元素                                |
| 主轴      |  Main Axis      | 主轴及其方向由 `flex-direction` 的值决定。           |
| 辅轴      |  Cross Axis     | 辅轴垂直于主轴。⚠️ MDN 将 Cross Axis 译作**侧轴**。   |

显然，上述 🌰 中的 section 是 flex 容器，article 是 flex 子项。

### 默认行为
* flex 子项等高。
* flex 子项撑满 flex 容器高度。
* flex 容器中的 flex 子项呈单行排布，不换行。
* flex 容器的布局方向是从左往右(对于阅读方向是从左往右的语言，如中文)。

💡 在 flex 容器上设置属性 `dir="rtl"` 可以使默认布局方向变成从右往左，不过这不是推荐的做法。

## flex-flow
[`flex-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow) 是以下两个属性的缩写。
* [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) 属性用于指定 flex 布局的方向。
* [`flex-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap) 属性用于指定 flex 布局是否换行。

### flex-direction
* `row` `默认值` 从左往右 ➡️
* `row-reverse` 从右往左 ⬅️
* `column` 从上往下 ⬇️
* `column-reverse` 从下往上 ⬆️

⚠️ `row` 和 `row-reverse` 的实际方向受 `dir` 属性影响。此处假设文本方向为**从左到右**。

### flex-wrap
* `nowrap` `默认值` 不换行，即 flex 子项都在同一行。
* `wrap` 换行(当空间不足时)。
* `wrap-reverse` 换行，但辅轴的开始和结束位置互换。

## order
[order](https://developer.mozilla.org/en-US/docs/Web/CSS/order) 属性用于指定 flex 子项的顺序。
* `0` `默认值`
* <整数>

## justify-content
[`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content) 属性用于指定**主轴方向**上 flex 子项之间及其周围的空间。
* `flex-start` `默认值`
* `flex-end`
* `center`
* `space-between`
* `space-around`

以下是 `flex-direction: row` 情况下，`justify-content` 各个值的效果示意图。  
![](https://css-tricks.com/wp-content/uploads/2013/04/justify-content.svg)

## align-content
[`align-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)

⚠️ `align-content`

![](https://css-tricks.com/wp-content/uploads/2013/04/align-content.svg)

## align-items
[`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
* `stretch` `默认值`

![](https://css-tricks.com/wp-content/uploads/2014/05/align-items.svg)

## margin: auto

## 属性列表
### flex 容器属性
* `flex-flow`
  * `flex-direction`
  * `flex-wrap`
* `justify-content` `主轴`
* `align-items` `辅轴`
* `align-content` `辅轴`

### flex 子项属性
* `order`
* `align-self` `辅轴`
* `flex`
  * `flex-grow`
  * `flex-shrink`
  * `flex-basis`

## 游戏教程 🎮
* https://flexboxfroggy.com

## 开源项目
* [Bootstrap 4](http://getbootstrap.com)

## 参考链接
* https://www.w3.org/TR/css-flexbox-1
* https://css-tricks.com/snippets/css/a-guide-to-flexbox
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Advanced_layouts_with_flexbox
* https://stackoverflow.com/questions/31250174/css-flexbox-difference-between-align-items-and-align-content
* https://stackoverflow.com/questions/32551291/in-css-flexbox-why-are-there-no-justify-items-and-justify-self-properties
