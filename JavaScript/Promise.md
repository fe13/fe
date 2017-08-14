# Promise

Promise 代表一个异步操作的最终完成(或失败)及其结果值。💡 Promise 意为**诺言**。

Promise 有三种可能的状态 

| 状态       | 说明         |
|-----------|-------------|
| `pending` | 未定 `初始值` | 
|`resolved` | 兑现         |
| `rejected`| 拒绝         |

## 许下诺言 new Promise(executor)
许下一个诺言
```javascript
> let promise = new Promise(function(resolve, reject) {})
→ undefined

> promise
→ Promise {[[PromiseStatus]]: "pending", [[PromiseValue]]: undefined}
```

许下一个诺言并马上兑现
```javascript
> let 一起看电影 = new Promise(function(resolve, reject) { resolve('战狼2'); })
→ undefined

> 一起看电影
→ Promise {[[PromiseStatus]]: "resolved", [[PromiseValue]]: "战狼2"}
```

许下一个诺言，想了一秒钟，拒绝(原因：今晚要上课)。
```javascript
> let 一起打篮球 = new Promise(function(resolve, reject) { setTimeout(() => reject('今晚要上课'), 1000); })
→ undefined

× Uncaught (in promise) 今晚要上课

> 一起打篮球
→ Promise {[[PromiseStatus]]: "rejected", [[PromiseValue]]: "今晚要上课"}
```
💡 `resolve` 和 `reject` 是 Promise 提供的函数。

💡 `new Promise(executor)` 中的 `executor` 函数在 Promise 初始化的时候立即执行。

## 然后怎样 then()
Promise 的值无法直接获取，需要调用 `then()` 方法。
```javascript
let trip = new Promise((resolve, reject) => {
  setTimeout(() => resolve('香港 🇭🇰'), 1000);
});

let hk = trip.then(function(place) {
  return place;
});

let au = hk.then(place => {
    return `${place} -> 泰国 🇹🇭`;        // 香港 🇭🇰
  })
  .then(places => {
    console.log(places);                // 香港 🇭🇰 -> 泰国 🇹🇭
    return `${places} -> 新加坡 🇸🇬`;
  })
  .then(places => {
    console.log(places);                // 香港 🇭🇰 -> 泰国 🇹🇭 -> 新加坡 🇸🇬
    return new Promise((resolve, reject) => {
      setTimeout(() => resolve(`${places} -> 新西兰 🇳🇿`), 3000);
    });
  })
  .then(places => {
    console.log(places);                // 香港 🇭🇰 -> 泰国 🇹🇭 -> 新加坡 🇸🇬 -> 新西兰 🇳🇿
    return new Promise((resolve, reject) => {
      setTimeout(() => resolve(`${places} -> 澳洲 🇦🇺`), 1500);
    });
  })
  .then(places => {
    console.log(places);                // 香港 🇭🇰 -> 泰国 🇹🇭 -> 新加坡 🇸🇬 -> 新西兰 🇳🇿 -> 澳洲 🇦🇺
    return places;
  });
```

## 如果不行 catch()
```javascript
let play = new Promise(function(resolve, reject) { 
  setTimeout(() => reject(new Error('不好意思😅，今晚要上课')), 1000);     // 通常用 Error 表示拒绝原因
});

play.catch(function(error) {
  console.log(error.message);
});
```
事实上，`catch()` 是 `then(null, onReject)` 的缩写。
```javascript
let home = au.then(() => {
  return Promise.reject(new Error('钱💰花🌺光了，肥家！'));
}).then(null, error => {
  console.log(error.message);
  return '家🏡';
});
```


## Promise API
### Promise.resolve()

### Promise.reject()

### Promise.all()

### Promise.race()

## 视频教程
* https://www.youtube.com/watch?v=vQ3MoXnKfuQ

## 参考链接
* [Promise A+ 规范](https://promisesaplus.com)
* http://callbackhell.com
* https://davidwalsh.name/promises
* https://github.com/mzabriskie/axios
* http://javascript.info/promise-basics
* http://javascript.info/promise-api
* http://javascript.info/promise-chaining
* https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all
* https://developers.google.com/web/fundamentals/getting-started/primers/promises
