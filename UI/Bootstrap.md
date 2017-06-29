# Bootstrap

Bootstrap 是一套开源的前端 UI 框架，包含众多通用的 UI 组件，插件丰富，特别适合快速开发网站，内部系统等。

## 导入
可通过 CDN 导入 Bootstrap，也可以下载后在本地引用。
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <link href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet">
  <title>Bootstrap</title>
</head>
<body>
  <script src="https://cdn.bootcss.com/jquery/3.2.1/jquery.min.js"></script>
  <script src="https://cdn.bootcss.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</body>
</html>
```

## 容器
`.container` `响应式`
```html
 <header>
   <div class="container">
     <h1>响应式设计</h1>
   </div>
 </header>
```
`.container-fluid` `非响应式`
```html
<div class="container-fluid">
  <p>在我的后园，可以看见墙外有两株树，一株是枣树，还有一株也是枣树。</p>
</div>
```

## 文本
* `.lead` 突出段落文字
* `.text-center` 文字居中
* `.text-left` 文字左对齐
* `.text-right` 文字右对齐
* `.list-unstyled` 去除列表默认样式
* `.list-inline` 行内列表
* `<i class="glyphicon glyphicon-globe"></i>` 字体图标

## 按钮
```html
<button type="button" class="btn btn-default">默认按钮</button>
<button type="button" class="btn btn-primary">首选按钮</button>
<button type="button" class="btn btn-success">成功按钮</button>
<button type="button" class="btn btn-info">提示按钮</button>
<button type="button" class="btn btn-warning">警告按钮</button>
<button type="button" class="btn btn-danger">危险按钮</button>
```

## 导航
* `<ul class="nav">` 局部导航基础类
* `<ul class="nav nav-tabs">` 标签页导航
* `<ul class="nav nav-pills">` 按钮式导航
* `<ul class="nav navbar-nav">` 整体导航栏内的子导航
* `<ul class="nav navbar-nav navbar-right">` 整体导航栏内的子导航(向右浮动)
* `<nav class="navbar navbar-default">` 整体导航栏容器
* `<nav class="navbar navbar-default navbar-static-top">` 整体导航栏容器(页面上方，静态定位)
* `<nav class="navbar navbar-inverse">` 整体导航栏容器(深色)
* `<nav class="navbar navbar-inverse navbar-fixed-bottom">` 整体导航栏容器(页面下方，固定定位)

```html
<nav class="navbar navbar-default navbar-static-top">
  <div class="container">
    <div class="navbar-header">
      <a class="navbar-brand" href="#">🍎</a>
    </div>
  </div>
</nav>
```

## 栅格
| 📱 Phone `<768px` | Pad `>=768px`    | 💻 Laptop `>=992px` | 🖥 Desktop `>=1200px` |
|:-----------------:|:----------------:|:------------------:|:---------------------:|
|      `col-xs-`    |   `col-sm-`      |     `col-md-`      |     `col-lg-`         |
|  `col-xs-offset-` | `col-sm-offset-` |  `col-md-offset-`  |   `col-lg-offset-`    |
|     `hidden-xs`   |    `hidden-sm`   |     `hidden-md`    |      `hidden-lg`      |
|    `visible-xs`   |   `visible-sm`   |    `visible-md`    |      `visible-lg`     |

```html
<div class="players">
  <div class="container-fluid">
    <div class="row">
      <div class="col-xs-12 col-sm-4">
        <div class="player lc">
          <p class="name">流川枫</p>
        </div>
      </div>
      <div class="col-xs-12 col-sm-4">
        <div class="player ym">
          <p class="name">樱木花道</p>
        </div>
      </div>
      <div class="col-xs-12 col-sm-4">
        <div class="player cm">
          <p class="name">赤木刚宪</p>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-xs-12 col-sm-4">
        <div class="player sj">
          <p class="name">三井寿</p>
        </div>
      </div>
      <div class="col-xs-12 col-sm-4">
        <div class="player gc">
          <p class="name">宫城良田</p>
        </div>
      </div>
      <div class="col-xs-12 col-sm-4">
        <div class="player mm">
          <p class="name">木暮公延</p>
        </div>
      </div>
    </div>
  </div>
</div>
```
🌰 https://twhy.github.io/slamdunk

## 参考链接
* [Bootstrap 优站精选](http://expo.bootcss.com)
* http://getbootstrap.com
* 🇨🇳 http://www.bootcss.com
