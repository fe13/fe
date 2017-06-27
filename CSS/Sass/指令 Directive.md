# 指令 Directive

## 控制指令
### @if

### @for

### @while

## @mixin
```sass
// Bootstrap 源码
@mixin text-truncate() {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
```
## @include


## @content


## 函数指令
* @function
* @return
```
@function px2rem(val, per: 125%) {
  @return (val / (16px * per))rem;
}
```

