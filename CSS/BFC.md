# BFC

## 什么是 BFC ?
BFC 全称是 Block Formatting Context。

一个 BFC 是网页中某个独立的 CSS 渲染区域。    

类似集团下一个独立运营的子公司；类似 JavaScript 的函数，拥有自己的作用域。

## BFC 何时产生 ？
* 根元素或包含它的其他元素
* 浮动元素
* `position: absolute` 和 `position: fixed` 的元素
* `display: inline-block` 的元素
* `overflow` 被设置成 `visible` 外的值的块状元素
* `<td>` 和 `display: table-cell` 的元素
* `<caption>` 和 `display: table-caption` 的元素
* `display: flow-root` 的元素
* `column-span: all` 的元素

## BFC 的特性
### 令外边距不坍塌
### 抑制浮动
### 包含浮动

## 参考链接
* http://lucybain.com/blog/2015/css-block-formatting-context/
* http://tech.vg.no/2013/09/26/css-block-formatting-context/
* https://yuiblog.com/blog/2010/05/19/css-101-block-formatting-contexts/
* http://maxdesign.com.au/jobs/sample-block-formatting-context/index.htm (包含很多例子)
* https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context
