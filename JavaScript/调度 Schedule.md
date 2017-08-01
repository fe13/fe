# 调度 Schedule

有时我们不希望马上执行函数，而且等待一段时间再执行。一般有以下两种方式：
* 延时执行 `setTimeout()` 方法在在指定时间后执行某个函数。

* 重复执行 `setInterval()` 方法以指定的时间间隔重复执行某个函数。

## 延时执行
### setTimeout()
```javascript
setTimeout(function() {
  console.log('GO! 🏎');
}, 3 * 1000);
```
IE9+ 的 `setTimeout()` 支持给函数传递参数。
```javascript
function launch(target, icon) {
  console.log(`发射${target} ${icon}`);
}

setTimeout(launch, 3000, '火箭', '🚀');
setTimeout(launch, 5000, '卫星', '🛰');
```

### clearTimeout()
`clearTimeout()` 方法用于清除 `setTimetout()` 设置的定时器。
```javascript
var timerId = setTimeout(function() {
  console.log('⏰⏰⏰');
}, 60 * 60 * 1000);     // 再睡一个小时

setTimeout(function() {
  clearTimeout(timerId);
}, 5 * 1000);           // 5 秒之后取消闹钟 ⏰
```

## 重复执行
### setInterval()
```javascript
var intervalId = setInterval(function() {
  console.log('喃唔呃尼陀佛', new Date());
}, 1000);
```

### clearInterval()
```javascript
clearInterval(intervalId);       // 🐒 表示很不耐烦
```

## 参考链接
* [setTimeout(fn, 0) 的作用](http://pandacafe.net/post/337)
* https://javascript.info/settimeout-setinterval
* https://www.w3.org/TR/html5/webappapis.html#timers
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval
* https://stackoverflow.com/questions/779379/why-is-settimeoutfn-0-sometimes-useful
