# 递归 Recursion

> 为了理解递归，首先你要理解递归。 -- CS106B

```javascript
function appearance(content, search) {
  let index = content.indexOf(search);
  if (index === -1) return 0;
  return 1 + appearance(content.slice(index + 1), search);
}
```

## 视频教程
* [斯坦福大学 CS106B - Recursion](https://www.youtube.com/watch?v=9vIyTn7ayac&list=PL-LN93ysLKsx94GK5pdLoQxfJbBHEUMir&index=14)
