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

## 栅格
| 📱 Phone `<768px` | Pad `>=768px`    | 💻 Laptop `>=992px` | 🖥 Desktop `>=1200px` |
|:-----------------:|:----------------:|:------------------:|:---------------------:|
|      `col-xs-`    |   `col-sm-`      |     `col-md-`      |     `col-lg-`         |
|  `col-xs-offset-` | `col-sm-offset-` |  `col-md-offset-`  |   `col-lg-offset-`    |
|     `hidden-xs`   |    `hidden-sm`   |     `hidden-md`    |      `hidden-lg`      |
|    `visible-xs`   |   `visible-sm`   |    `visible-md`    |      `visible-lg`     |

* `.row`
* `.col-md-12`
* `.col-md-8`
* `.col-md-3`
* `.col-md-offset-1`
* `.col-sm-offset-0`

## 文本
* `.lead` 突出段落文字
* `.text-center` 文字居中
* `.text-left` 文字左对齐
* `.text-right` 文字右对齐
* `.list-unstyled` 去除列表默认样式
* `.list-inline` 行内列表
* `<i class="glyphicon glyphicon-globe"></i>` 字体图标

## 导航

## 参考链接
* [Bootstrap 优站精选](http://expo.bootcss.com)
* http://getbootstrap.com
* 🇨🇳 http://www.bootcss.com
