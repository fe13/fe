# 动态规划 Dynamic Programming

## Fibonacci 数列
| 索引 | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10  |  ...  |
|-----|---|---|---|---|---|---|---|---|---|---|------|------|
| 数字 | 0 | 1 | 1 | 2 | 3 | 5 | 8 | 13 | 21 | 34 | 55 | ... | 
```javascript
function fibonacci(n) {
  let numbers = [0, 1];
  return fib(n);

  function fib(x) {
    if (numbers[x] === void 0) numbers[x] = fib(x - 1) + fib(x - 2);
    return numbers[x];
  }
}
```
```javascript
> fibonacci(0)
→ 0

> fibonacci(1)
→ 1

> fibonacci(3)
→ 2

> fibonacci(6)
→ 8

> fibonacci(10)
→ 55
```


## Youtube 视频
* [Dynamic Programming 播放列表 - CSBreakdown](https://www.youtube.com/playlist?list=PLyEvk8ZeQDMVbsg7CEfT0NV3s3GkMx1vN)

## 参考链接
* [背包问题九讲](http://love-oriented.com/pack)
* https://www.topcoder.com/community/data-science/data-science-tutorials/dynamic-programming-from-novice-to-advanced
* https://www.hackerearth.com/practice/algorithms/dynamic-programming/introduction-to-dynamic-programming-1/tutorial
