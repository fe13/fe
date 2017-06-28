# 嵌套 Nesting

Sass 允许嵌套规则，便于维护样式代码。

`SCSS`
```sass
.header {
  height: 60px;
  .navbar {
    display: flex;
    > li {
      flex: 1;
      a {
        dislay: block;
        font-size: 18px;
      }
    }
  }
}
```
`CSS`
```css
.header {
  height: 60px;
}
.header .navbar {
  display: flex;
}
.header .navbar > li {
  flex: 1;
}
.header .navbar > li a {
  dislay: block;
  font-size: 18px;
}
```

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
