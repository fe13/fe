# 指令 Directive

## 控制指令
### @if

### @for

### @while

### @each

#### @each 遍历键值对
`SCSS`
```sass
$frameworks: (vue: 'vue.png', angular: 'angular.svg', react: 'react.jpg');

@each $framework, $icon in $frameworks {
  .framework.#{$framework} {
    background-image: url(../images/#{$icon});
  }
}
```
`CSS`
```css
.framework.vue {
  background-image: url(../images/vue.png);
}

.framework.angular {
  background-image: url(../images/angular.svg);
}

.framework.react {
  background-image: url(../images/react.jpg);
}
```

## @content


## 函数指令
* @function
* @return
```sass
@function px2rem($val, $per: .625) {
  @return #{$val / (16 * $per)}rem;
}

.container {
  max-width: px2rem(1000);
}
```

## 参考链接
* https://hugogiraudel.com/2013/08/08/advanced-sass-list-functions
