# 嵌套 Nesting

## & 引用
`SCSS`
```sass
.flex-item {
  .no-flexbox & {
    float: left;
  }
}
```
`CSS`
```css
.no-flexbox .flex-item {
  float: left;
}
```

`SCSS`
```sass
.container {
  > .navbar {
    .header > & {
      background: deepskyblue;
    }
  }
}
```
`CSS`
```css
.header > .container > .navbar {
  background: deepskyblue;
}
```
