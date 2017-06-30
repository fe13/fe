# 变量 Variable

## 变量 $
在 Sass 中通过 `$` 声明变量。

`SCSS`
```sass
$root-font-size: 10px;

html {
  font-size: $root-font-size;
}
```

`CSS`
```css
html {
  font-size: 10px;
}
```

## 默认值 !default
通过 `!default` 可以给变量设置默认值。

`SCSS`
```sass
$content: '🍏';
$content: '🍎' !default;

.apple-icon::after {
  content: $content;
}
```
`CSS`
```css
@charset "UTF-8";
.apple-icon::after {
  content: "🍏";
}
```

## 数据类型
`SCSS`
```sass
// 数字
$font-size: 2rem;
$line-height: 1.5;

// 颜色
$base: darkorange;
$link-color: #0070e9;
$overlay-bg-color: rgba(255, 255, 255, .5);

// 空值
$animate: null;

// 字符串
$greeting: How are you;
$response: "Fine, thank you, and you?";
$content: 吾生也有涯，而知也无涯。;

// 布尔值
$hd: true;
$use-dark-theme: false;

// 键值对 Map
$frameworks: (vue: 'vue.png', angular: 'angular.svg', react: 'react.jpg');

// 列表 List
$padding: 20px 10px 30px 40px;
$font-family: Helvetica, Arial, sans-serif;
$warriors: curry, klay, durant, green, zaza;
```




## 插值 Interpolation
`SCSS`
```sass
$side: bottom;

.header {
  border-#{$side}: 1px solid #ccc;
}
```
`CSS`
```css
.header {
  border-bottom: 1px solid #ccc;
}
```

