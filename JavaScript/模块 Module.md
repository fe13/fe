# 模块 Module

`ES6`(ES2015) 为 JavaScript 带来了语言层面的模块特性。

## export
`export` 语句用于**导出**模块内的类，函数，对象，数值等。

`music_player.js`
```javascript
export class Slider {
  // ...
}
```
`lazyload.js`
```javascript

export function lazyload(images) {
  // ...
}
```
`constants.js`
```javascript
export const TOPLIST_URL = 'https://qq-music-api.now.sh/top'
// ...
```

## import
`import` 语句用于**导入**模块内的类，函数，对象，数值等。

`toplist.js`
```javascript
import { lazyload } from './lazyload' 
import { TOPLIST_URL } from './constants'

export class TopList {
  // ...
}
```

## 参考链接
* https://ponyfoo.com/articles/es6-modules-in-depth
* https://jakearchibald.com/2017/es-modules-in-browsers
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export
