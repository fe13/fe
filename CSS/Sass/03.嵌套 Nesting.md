# 嵌套 Nesting

Sass 允许嵌套规则，便于维护样式代码。

## 嵌套规则
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

## 嵌套属性
CSS 属性也是可以嵌套的。

`SCSS`
```sass
.fancy {
  font: {
    size: 12rem;
    weight: bold;
    family: fantasy;
  }
}
```
`CSS`
```css
.fancy {
  font-size: 12rem;
  font-weight: bold;
  font-family: fantasy;
}
```

## & 引用
Sass 提供了 `&` 用于引用父选择器。

`SCSS`
```sass
.btn {
  &.btn-default { background: #ffffff; }
  &.btn-primary { background: #337ab7; }
  &.btn-success { background: #5cb85c; }
}
```
`CSS`
```css
.btn.btn-default {
  background: #ffffff;
}
.btn.btn-primary {
  background: #337ab7;
}
.btn.btn-success {
  background: #5cb85c;
}
```

在 `&` 前面添加选择器是 🆗 的。

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

在 `&` 后面添加后缀也是 🆗 的。

`SCSS`
```sass
.product {
  &-title {
    font-size: 3rem;
  }
  &-price {
    font-size: 2rem;
  }
}
```

`CSS`
```css
.product-title {
  font-size: 3rem;
}
.product-price {
  font-size: 2rem;
}
```

多重嵌套中使用 `&` 要特别注意，以下 🌰 中 `&` 代表 `.container > .navbar`。

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
