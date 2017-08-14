# Promise

Promise 代表一个异步操作的最终完成(或失败)及其结果值。💡 Promise 意为**诺言**。

Promise 有三种可能的状态 

| 状态       | 说明         |
|-----------|-------------|
| `pending` | 未定 `初始值` | 
|`fulfilled`| 兑现         |
| `rejected`| 拒绝         |

```javascript
> new Promise((resolve, reject) => {})
→ Promise {[[PromiseStatus]]: "pending", [[PromiseValue]]: undefined}
```

## Promise API

## 参考链接
* [Promise A+ 规范](https://promisesaplus.com)
* http://callbackhell.com
* https://davidwalsh.name/promises
* https://github.com/mzabriskie/axios
* http://javascript.info/promise-basics
* http://javascript.info/promise-api
* https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all
* https://developers.google.com/web/fundamentals/getting-started/primers/promises
