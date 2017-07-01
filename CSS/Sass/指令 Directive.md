# 指令 Directive

## 函数指令
### 定义函数
`@function` 定义函数，

`SCSS`
```sass
$font-size-base: 12px;  // 中文版 Chrome 限制最小字体大小为 12px

@function px2rem($px) {
  @return #{($px / $font-size-base)}rem;
}

.container {
  width: px2rem(1000px);
}
```

`CSS`
```css
.container {
  width: 83.33333333rem;
}
```

### 内置函数
`SCSS`
```sass
// rgba()
$bgcolor: #ccc;

.overlay {
  background-color: rgba($bgcolor, .8);
}

// lighten($color, $amount) darken($color, $amount)
$link-color: #0070e9;

a {
  color: $link-color;
  &:hover { color: lighten($link-color, 10%); };
  &:active { color: darken($link-color, 10%); };
}

// length($list) 获取列表长度
$fruits: apple banana orange pear stawberry cherry kiwi;
$len: length($fruits);   // 7

// nth($list, $n) 获取列表第 n 个元素
$cherry: nth($fruits, 6);

// index($list, $item) 获取列表元素下标
$iorange: index($fruits, orange);  // 3
```
💡 [内置函数列表](http://sass-lang.com/documentation/Sass/Script/Functions.html)

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

## 参考链接
* http://sass-lang.com/documentation/Sass/Script/Functions.html
* https://hugogiraudel.com/2013/08/08/advanced-sass-list-functions
