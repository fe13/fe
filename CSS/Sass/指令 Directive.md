# 指令 Directive

## 控制指令
### @if
`@if` 结合 `@mixin` 和变量控制是否出现圆角。

`SCSS`
```sass
// from Bootstrap
$enable-rounded: true;

@mixin border-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-radius: $radius;
  }
}
```

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
`SCSS`
```sass
$warriors: sc, kd, ai, lv, dw, klay, zaza, green, clark, mcgee;
@each $name in $warriors {
  $i: index($warriors, $name) - 1;
  .warrior.#{$name} {
    background-image: url(../images/#{$name}.jpeg);
    transform: rotateY(360deg / length($warriors) * $i) translateZ(380px);
  }
}
```

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
