# 定位 Position 

## 正常/文档流 Normal Flow
Normal Flow 即浏览器默认的文档布局方式。

定位就是通过设置 [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) 属性的值来覆盖默认的布局方式。

* [top](https://developer.mozilla.org/en-US/docs/Web/CSS/top)
* [left](https://developer.mozilla.org/en-US/docs/Web/CSS/left)
* [right](https://developer.mozilla.org/en-US/docs/Web/CSS/right)
* [bottom](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom)

## 静态定位
`position: static` `默认值` 默认的布局方式。

## 相对定位
`position: relative` 相对默认的布局位置进行定位。

💡 相对定位就是“相对自己定位”。
```css
.avatar {
  top: 3px;
  left: 7px;
  position: relative;
}
```

## 绝对定位
`position: absolute` 绝对定位元素脱离正常文档流，相对其定位上下文（Positioning Context）进行定位。

### 定位上下文 Positioning Context
定位上下文就是值绝对定位元素相对哪个元素定位，默认的定位上下文是 `<html>`。

假如你想设定某个绝对定位元素的定位上下文，则需要在这个元素的某个祖先元素上设置 `position: relative`。

### z-index
```css
.feedback {
  z-index: 1; 
}
```

## 固定定位
`position: fixed` 相对浏览器窗口进行定位。因此当滚动产生时，固定定位元素依然处于窗口的某个固定位置。
```css
.feedback {
  right: 30px;
  bottom: 30px;
  position: fixed;
}
```

## 粘性定位
`position: sticky` 是相对定位和固定定位的结合。默认情况下表现为相对定位，当浏览器窗口顶端与元素的距离等于 `top` 属性的值时，转变为固定定位。

🌰 [Macbook Pro 产品导航栏](https://www.apple.com/macbook-pro)

🤔 `position` 属性有哪些值，它们的表现有什么不同？

## 参考链接
* https://css-tricks.com/almanac/properties/p/position
* https://css-tricks.com/absolute-relative-fixed-positioining-how-do-they-differ
* https://developer.mozilla.org/zh-CN/docs/Web/CSS/position
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning
* https://stackoverflow.com/questions/14391208/how-does-z-index-really-work
