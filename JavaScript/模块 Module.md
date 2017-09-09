# 模块 Module

`ES6`(ES2015) 为 JavaScript 带来了语言层面的模块特性。

## export
`export` 语句用于**导出**模块内的类，函数，对象，数值等。

```javascript
/* scripts/music_player.js */
export class MusicPlayer {
  // ...
}
```
```javascript
/* scripts/lazyload.js */
export function lazyload(images) {
  // ...
}
```

## import
`import` 语句用于**导入**模块内的类，函数，对象，数值等。

## 参考链接
* https://ponyfoo.com/articles/es6-modules-in-depth
* https://jakearchibald.com/2017/es-modules-in-browsers
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export
