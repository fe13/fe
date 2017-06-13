# Position 定位

## 正常/文档流 Normal Flow
Normal Flow 即浏览器默认的文档布局方式。

定位就是通过设置 `position` 属性的值来覆盖默认的布局方式。

## 静态定位
`position: static` `默认值` 默认的布局方式。

## 相对定位
`position: relative` 相对默认的布局位置进行定位。
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

## 固定定位
`position: fixed;`

## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning
