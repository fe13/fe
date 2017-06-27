# 变量 Variable

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

