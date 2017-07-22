# BFC

BFC 全称 Block Formatting Context。

一个 BFC 是网页中某个独立的 CSS 渲染区域。    

类似集团下一个独立运营的子公司；类似 JavaScript 的函数，拥有自己的作用域。

## BFC 的产生
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
> In a block formatting context, each box's left outer edge touches the left edge of the containing block (for right-to-left formatting, right edges touch). This is true even in the presence of floats (although a box's line boxes may shrink due to the floats), unless the box establishes a new block formatting context (in which case the box itself may become narrower due to the floats).

### 阻止外边距坍塌
### 抑制浮动
### 包含浮动

## 参考链接
* https://www.w3.org/TR/CSS2/visuren.html#block-formatting
* http://lucybain.com/blog/2015/css-block-formatting-context
* http://tech.vg.no/2013/09/26/css-block-formatting-context
* http://www.cnblogs.com/lhb25/p/inside-block-formatting-ontext.html
* https://yuiblog.com/blog/2010/05/19/css-101-block-formatting-contexts
* http://maxdesign.com.au/jobs/sample-block-formatting-context/index.htm
* https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context

