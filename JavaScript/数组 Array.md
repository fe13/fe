# 数组 Array

```javascript
var skills = ['卖萌', '碎觉', '瞪眼', '三分球', '各种语言的 Hello World'];
```

## 常用 API
`Array.prototype.push()` 用于往数组末尾添加 1 个或多个元素并返回新的数组长度。
```javascript
> var sx = ['🐭', '🐮', '🐯', '🐰'];
→ undefined

> sx.push('🐲')
→ 5

> sx
→ ["🐭", "🐮", "🐯", "🐰", "🐲"]

> sx.push('🐍', '🐴', '🐑', '🐵', '🐔', '🐶', '🐷');
→ 12

> sx
→ ["🐭", "🐮", "🐯", "🐰", "🐲", "🐍", "🐴", "🐑", "🐵", "🐔", "🐶", "🐷"]
```

## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push
