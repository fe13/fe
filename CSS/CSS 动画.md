# CSS 动画

`CSS3` CSS 动画可能是 CSS 中最有趣的部分。

## transition
[transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) 属性用于设置元素两种状态间的过渡动画，是以下四个属性的缩写。
* [transition-property](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property) 属性用于设置动画属性。
* [transition-duration](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration) 属性用于设置动画时长。
* [transition-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function) 属性用于设置动画时间函数。
* [transition-delay](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) 属性用于设置动画延时。

```css
.😎 {
  /* (所有)属性 | 时长 | 函数 | 延时 */
  transition: all 0.5s ease-out .2s;
}
```

**注意** 只有一部分 CSS 属性是可以 “动” 的，详见 MDN [CSS Animated Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)。

## transform
[transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) 用于
* `none`
* `perspective()` 函数用于指定视觉距离。🌰 距离屏幕 500px `perspective(500px)`
* `translate()` 函数用于指定**水平**和**垂直**位移。 🌰 `translate(-50%, -50%)`实现[垂直居中](https://codepen.io/twhy/pen/WOoqBr)
* `translateX()` 函数用于指定**水平**位移。🌰 `translateX(5px)`
* `translateY()` 函数用于指定**垂直**位移。🌰 `translateY(20%)`
* `translateZ()` 函数用于指定**垂直屏幕方向**位移 🌰 `transform: perspective(500px) translateZ(-300px)`
* `translate3d()`
* `skew()`
* `skewX()`
* `skewY()`
* `scale()`
* `scaleX()`
* `scaleY()`
* `scaleZ()`
* `scale3d()`
* `rotate()`
* `rotateX()`
* `rotateY()`
* `rotateZ()`
* `rotate3d()`
* `matrix()`
* `matrix3d()`

[transform-style](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style) 用于设置元素的子元素(s)是处于 3D 空间还是平面空间。
* `flat` 平面空间
* `preserve-3d` 3D 空间

[transform-origin](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)

## perspective
[perspective](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective)

## backface-visibility
[backface-visibility](https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility)

## animation
[@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) 用于自定义动画帧。

```css
@keyframes tooltip-appear {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
```

[animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) 属性用于设置应用在元素上的动画，是以下属性的缩写。
* [animation-name](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name)
* [animation-duration](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration)
* [animation-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)
* [animation-delay](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)
* [animation-iteration-count](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count)
* [animation-direction](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction)
* [animation-fill-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode)
* [animation-play-state](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state)

[animation-name](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) 属性用于指定应用到元素上的一个或多个动画。
* `none` 无动画，用于取消来自
* `<动画名称>` 通过 `@keyframes` 定义的动画名称

[animation-duration](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration) 属性用于指定动画时长。
```css
/* 单个动画 */
animation-duration: 5s;
animation-duration: 180ms;

/* 多个动画 */
animation-duration: 1.68s, 12.34s;
animation-duration: 8s, 23s, 370ms;
```

[animation-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function) 属性用于指定动画时间函数。

[animation-iteration-count](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count) 属性用于指定动画播放次数。
* `infinite` 无限循环播放
* `<数字>` 动画播放次数
```css
animation-iteration-count: infinite;
animation-iteration-count: 3;
animation-iteration-count: 2.3;
animation-iteration-count: 2, 0, infinite;
```

[animation-direction](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction) 属性用于指定动画的播放方向。
* `normal` `默认值` 从前往后播放
* `reverse` 从后往前播放，动画函数
* `alternate`
* `alternate-reverse`

[animation-play-state](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state) 属性用于指定动画的状态是运行或暂停，可通过 JavaScript 设置该属性的值以控制动画的播放状态。
* `paused` 暂停动画
* `running` 运行动画
```css
/* 单个动画 */
animation-play-state: running;
animation-play-state: paused;

/* 多个动画 */
animation-play-state: paused, running, running;
```

## 开源项目
* [Animate.css](https://daneden.github.io/animate.css/)

## 参考链接
* https://davidwalsh.name/css-flip
* https://davidwalsh.name/css-cube
* https://desandro.github.io/3dtransforms/
* https://css-tricks.com/creating-a-3d-cube-image-gallery/
* https://css-tricks.com/almanac/properties/a/animation/
* https://developer.mozilla.org/en-US/docs/Web/CSS/transition
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions

