# CSS 动画

`CSS3` CSS 动画可能是 CSS 中最有趣的部分。

## 轴与方向
| 轴    | 方向          |
|------|---------------|
| X 轴 | 元素平面水平方向 |
| Y 轴 | 元素平面垂直方向 |
| Z 轴 | 垂直元素所在平面 |


## transition
[transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) 属性用于设置元素两种状态间的过渡动画，是以下四个属性的缩写。
* [transition-property](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property) 属性用于设置动画属性。
* [transition-duration](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration) 属性用于设置动画时长。
* [transition-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function) 属性用于设置动画时间函数。
* [transition-delay](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) 属性用于设置动画延时。

```css
/* (所有)属性 | 时长 | 函数 | 延时 */
transition: all 0.5s ease-out 0.2s;

/* 单个属性 */
transition: width 2s ease-in-out;

/* 多个属性 */
transition: left 3s, color 2s, opacity 1s;
```

**注意** 只有一部分 CSS 属性是可以 “动” 的，详见 MDN [CSS Animated Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)。

## transform
[transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) 属性用于修改元素 VFM(Visual Formatting Model) 的坐标空间，以实现元素的位移，旋转，缩放，和倾斜。
* `none` 无变化 🙈
* `perspective()` 函数用于指定视觉距离。🌰 距离屏幕 500px `perspective(500px)`
* `translate()` 函数用于指定 **X 轴** 和 **Y 轴** 位移。 🌰 绝对定位 + `translate(-50%, -50%)`实现垂直居中 [Demo](https://codepen.io/twhy/pen/WOoqBr)
* `translateX()` 函数用于指定 **X 轴** 位移。🌰 `translateX(5px)`
* `translateY()` 函数用于指定 **Y 轴** 位移。🌰 `translateY(20%)`
* `translateZ()` 函数用于指定 **Z 轴** 位移。 🌰 `translateZ(-300px)`
* `translate3d()` 函数用于指定 **X 轴** **Y 轴** **Z 轴** 的位移。 🌰 `translate3d(50px, 20%, 300px)` `GPU 硬件加速`
* `skew()` 函数用于指定 **X 轴方向** 和 **Y 轴方向** 倾斜角度。🌰 `skew(20deg, 30deg)`
* `skewX()` 函数用于指定 **X 轴方向** 倾斜角度。🌰 `skewX(20deg)`
* `skewY()` 函数用于指定 **Y 轴方向** 倾斜角度。🌰 `skewY(30deg)`
* `scale()` 函数用于指定 **X 轴方向** 和 **垂直方向** 缩放。🌰 `scale(2, 1.2)` 😜 `scale(-2)`
* `scaleX()` 函数用于指定 **X 轴方向** 的缩放。🌰 `scaleX(2)`
* `scaleY()` 函数用于指定 **Y 轴方向** 的缩放。🌰 `scaleY(0.8)`
* `scaleZ()` 函数用于指定 **Z 轴方向** 的缩放。 🌰 `transform: perspective(500px) scaleZ(2) translateZ(100px)`
* `scale3d()` 函数用于指定 **X 轴** **Y 轴** **Z 轴方向** 的缩放。
* `rotate()` 函数用于指定元素沿 **Z 轴** 旋转的角度。因此 `rotate(90deg)` 等同于 `rotateZ(90deg)`。
* `rotateX()` 函数用于指定元素沿 **X 轴** 旋转的角度。🌰 `rotateX(45deg)`
* `rotateY()` 函数用于指定元素沿 **Y 轴** 旋转的角度。🌰 `rotateY(180deg)`
* `rotateZ()` 函数用于指定元素沿 **Z 轴** 旋转的角度。🌰 `rotateZ(90deg)`
* `rotate3d()` 函数用于指定元素在 3D 空间的旋转。 🌰 `transform: rotate3d(1, 2, -1, 192deg)`
* `matrix()` 函数指定一个由 6 个值组成的 2D 变换矩阵。
* `matrix3d()` 函数指定一个用于描述 3D 变换的 4x4 矩阵。

```css
transform: scale(1.2);

transform: translate3d(50px, 20%, 300px)

transform: perspective(500px) translateZ(-300px) rotateX(45deg);
```

[transform-style](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style) 用于设置元素的子元素(s)是处于 3D 空间还是平面空间。
* `flat` 平面空间
* `preserve-3d` 3D 空间

[transform-origin](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin) 用于设置元素变形的原点。

绕元素左上角旋转 45°
```css
transfrom-origin: 0 0;
transform: rotate(45deg);
```
🌰 迷之猴子 https://codepen.io/twhy/pen/Ngdpej

## perspective
[perspective](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective) 属性用于指定观察者与 z=0 平面的距离，使具有 3D 变换的元素产生透视效果。
```css
.container {
  pespective: 1000px;
}

.scene {
  transform: perspective(500px) translateZ(-300px);
}
```

[perspective-origin](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective-origin) 属性用于指定观察者的位置。

## backface-visibility
[backface-visibility](https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility) 属性用于设置元素背面是否可见。
* `visible` 元素背面可见
* `hidden` 元素背面不可见

🌰 翻转扑克 https://codepen.io/twhy/pen/mwRRdX

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
🌰 `:hover` 提示 https://codepen.io/twhy/pen/wegooP

通过百分比可定义更复杂的动画。**提示** `from` 等价于 `0%`， `to` 等价于 `100%`
```css
/* 
 *  code from Animate.css 
 *  https://github.com/daneden/animate.css/blob/master/source/lightspeed/lightSpeedIn.css
 */
@keyframes lightSpeedIn {
  from {
    transform: translate3d(100%, 0, 0) skewX(-30deg);
    opacity: 0;
  }

  60% {
    transform: skewX(20deg);
    opacity: 1;
  }

  80% {
    transform: skewX(-5deg);
    opacity: 1;
  }

  to {
    transform: none;
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

```css
animation: spin 20s linear infinite;
```

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
* `normal` `默认值` 从前往后播放。
* `reverse` 从后往前播放，动画函数也会被翻转，如 `ease-in` 变成 `ease-out`。
* `alternate` 先从前往后，再从后往前，如此交替。
* `alternate-reverse` 先从后往前，再从前往后，如此交替。

[animation-fill-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode) 属性用于指定在动画执行前后如何给元素应用样式。
* `none` `默认值`
* `forwards` 保持动画最后一帧的样式，最后一帧取决于 `animation-direction` 和 `animation-iteration-count`。
* `backwards` 动画采用第一帧的样式，保持 `animation-delay`，第一帧取法由 `animation-direction` 决定。
* `both` 动画执行 `forwards` 和 `backwards` 执行的动作。

[animation-play-state](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state) 属性用于指定动画的状态是运行或暂停，可通过 JavaScript 设置该属性的值以控制动画的播放状态。
* `running` 运行动画
* `paused` 暂停动画

```css
/* 单个动画 */
animation-play-state: running;
animation-play-state: paused;

/* 多个动画 */
animation-play-state: paused, running, running;
```
🌰 `:hover` 叫车 https://codepen.io/twhy/pen/zzNGKV

## 常见动画
* 翻转扑克 https://codepen.io/twhy/pen/mwRRdX
* 正立方体 https://twhy.github.io/fruit-cube
* 3D 轮播 https://twhy.github.io/warriors-champions-2017

以上三种常见动画共同点
```html
<div class="scene">
  <div class="object">
    <div class="face"></div>
    <div class="face"></div>
    <div class="face"></div>
    ...
  </div>
</div>
```
```css
.scene {
  perspective: 1000px;  /* 设置视觉距离 */
  ...
}

.object {
  position: relative;
  transform-style: preserve-3d;  /* 保持子元素 3D 变换效果 */
  ... /* 设置宽高等属性 */
}

.face {
  top: 0;
  left: 0;
  width: inherit;
  height: inherit;
  position: absolute;
  ... /* 每个子元素设置不同的 transform 值 */
}
```

## 开源项目
* [Animate.css](https://daneden.github.io/animate.css)

## 动画工具
* http://cubic-bezier.com
* http://isux.tencent.com/css3/tools.html

## 参考链接
* http://kushagragour.in/about
* https://davidwalsh.name/css-flip
* https://davidwalsh.name/css-cube
* https://desandro.github.io/3dtransforms
* https://taosang1992.github.io/my-works/WebDemo/app01
* https://css-tricks.com/creating-a-3d-cube-image-gallery
* https://css-tricks.com/almanac/properties/a/animation
* https://www.smashingmagazine.com/2014/04/understanding-css-timing-functions
* https://developer.mozilla.org/en-US/docs/Web/CSS/transition
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions
