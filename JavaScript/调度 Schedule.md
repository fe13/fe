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
clearInterval(intervalId);       // 齐天大圣 🙉 表示很不耐烦
```

### 充电动画
结合 `setTimeout()` `setInterval()` 和 FontAwesome 实现充电动画。
```html
<i id="battery" class="fa fa-battery-0"></i>
```
```javascript
let $battery = document.querySelector('#battery');

function charge() {
  setTimeout(function() {
    $battery.classList.remove('fa-battery-0', 'fa-battery-4');
    $battery.classList.add('fa-battery-1');
  }, 1000);
  
  setTimeout(function() {
    $battery.classList.remove('fa-battery-1');
    $battery.classList.add('fa-battery-2');
  }, 2000);
  
  setTimeout(function() {
    $battery.classList.remove('fa-battery-2');
    $battery.classList.add('fa-battery-3');
  }, 3000);
  
  setTimeout(function() {
    $battery.classList.remove('fa-battery-3');
    $battery.classList.add('fa-battery-4');
  }, 4000);
}

setInterval(charge, 4000);
```
🚀 https://codepen.io/twhy/pen/mMPjMB

### 递归 setTimeout()
递归地调用 `setTimeout()` 也可以实现重复执行。
```javascript
let sheep = {
  name: '绵羊',
  icon: '🐑'
  count: 0,
}

function count(animal) {
  animal.count += 1;
  console.log(`${animal.count} 只${animal.name} ${animal.icon.repeat(animal.count)}`);
}

setTimeout(function run() {
  count(sheep);
  setTimeout(run, 1000);
}, 1000);
```
💡 这种方式能保证每次调用 `sheep()` 之间有固定间隔(本例中是 1s)。

```javascript
let tiger = {
  name: '老虎',
  icon: '🐯',
  count: 0
};

setInterval(function() {
  count(tiger);
}, 1000);
```

## 参考链接
* [setTimeout(fn, 0) 的作用](http://pandacafe.net/post/337)
* https://javascript.info/settimeout-setinterval
* https://www.w3.org/TR/html5/webappapis.html#timers
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval
* https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval
* https://developer.mozilla.org/en-US/docs/Web/API/Window/setImmediate
* https://developer.mozilla.org/en-US/docs/Web/API/Window/clearImmediate
* https://stackoverflow.com/questions/779379/why-is-settimeoutfn-0-sometimes-useful
