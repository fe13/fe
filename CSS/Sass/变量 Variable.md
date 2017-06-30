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
### 列表 List
`SCSS`
```sass
$padding: 20px 10px 30px 40px;
$warriors: curry, klay, durant, green, zaza;
```

### 键值对 Map
`SCSS`
```

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

