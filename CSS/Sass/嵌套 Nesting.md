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
CSS 属性也可以嵌套，只是不太常用。

`SCSS`
```sass
.footer {
  border: {
    top: 1px dotted #aaa;
    left: 2px dashed #bbb; 
    right: 3px solid #ccc;
    bottom: 4px double #ddd;
  };
}
```
`CSS`
```css
.footer {
  border-top: 1px dotted #aaa;
  border-left: 2px dashed #bbb;
  border-right: 3px solid #ccc;
  border-bottom: 4px double #ddd;
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
