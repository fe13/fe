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

### display: inline-flex

## 游戏教程 🎮
* https://flexboxfroggy.com/

## 参考链接
* https://davidwalsh.name/css-reverse
* https://css-tricks.com/snippets/css/a-guide-to-flexbox/
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox
