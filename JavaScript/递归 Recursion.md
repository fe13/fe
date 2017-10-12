# 递归 Recursion

> 为了理解递归，首先你要理解递归。 -- CS106B

计算 `n` 的阶乘 `n!` 💡 `5! = 5 * 4 * 3 * 2 * 1 = 120`
```javascript
function factorial(x) {
  return n > 1 ? n * factorial(n - 1) : 1
}
```

## 视频教程
* [斯坦福大学 CS106B - Recursion](https://www.youtube.com/watch?v=9vIyTn7ayac&list=PL-LN93ysLKsx94GK5pdLoQxfJbBHEUMir&index=14)
