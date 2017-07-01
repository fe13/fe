# 指令 Directive

## 控制指令
### @if
`@if` 结合 `@mixin` 和变量实现全局控制是否出现圆角。

`SCSS`
```sass
// from Bootstrap
$enable-rounded: true;

@mixin border-radius($radius: $border-radius) {
  @if $enable-rounded {
    border-radius: $radius;
  }
}

.btn {
  @include border-radius(4px);
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
### 定义函数
`@function` 定义函数，

`SCSS`
```sass
$font-size-base: 12px;  // 中文版 Chrome 限制最小字体大小为 12px

@function px2rem($px, $base: $font-size-base) {
  @return #{($px / $base)}rem;
}

.container {
  width: px2rem(1000px);
}
```

### 内置函数
`SCSS`
```
// length()

// index()

// rgba()

// darken()

// lighten()

// saturate()

// desaturate()
```

## 参考链接
* http://sass-lang.com/documentation/Sass/Script/Functions.html
* https://hugogiraudel.com/2013/08/08/advanced-sass-list-functions
