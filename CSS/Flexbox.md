# Flexbox

Flexbox 为 CSS 提供了更简单更强大的布局方式。

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
**运行结果** https://codepen.io/twhy/pen/MopwzL

`display: inline-flex`

### Flex 术语
| 术语      | 英文            | 含义                     |
|----------|-----------------|-------------------------|
| flex 容器 |  flex container | `display: flex` 的父元素 |
| flex 子项 |  flex items     | flex 容器中的子元素       |

很明显，上述 🌰 中的 section 是 flex 容器，article 是 flex 子项。

## flex-flow
[`flex-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow) 是以下两个属性的缩写。
* [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)
* [`flex-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap)

### flex-direction
* `row` `默认值`
* `row-reverse`
* `column`
* `column-reverse`

### flex-wrap
* `nowrap` `默认值`
* `wrap`
* `wrap-reverse`

### 轴与方向

## flex

## order
[order](https://developer.mozilla.org/en-US/docs/Web/CSS/order)
* `0` `默认值`
* <整数>

### justify-content
[`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)
* `flex-start`
* `flex-end`
* `center`
* `space-between`
* `space-around`

## 属性列表
* `display`
  * `display: flex`
  * `display: inline-flex`
* `flex-flow`
  * `flex-direction`
  * `flex-wrap`
* `order`
* `justify-content` `主轴`
* `align-self` `辅轴`
* `align-items` `辅轴`
* `align-content` `辅轴`
* `flex`
  * `flex-grow`
  * `flex-shrink`
  * `flex-basis`

## 游戏教程 🎮
* https://flexboxfroggy.com

## 开源项目
* [Bootstrap 4](http://getbootstrap.com)

## 参考链接
* https://davidwalsh.name/css-reverse
* https://css-tricks.com/snippets/css/a-guide-to-flexbox
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Advanced_layouts_with_flexbox
