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

## 列表 List
`SCSS`
```sass
$padding: 20px 10px 30px 40px;
$warriors: curry, klay, durant, green, zaza;
```

## 键值对 Map

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

