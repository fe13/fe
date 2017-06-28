# Bootstrap

Bootstrap 是一套开源的前端 UI 框架，包含众多通用的 UI 组件，插件丰富，特别适合快速开发网站，内部系统等。

## 导入 Bootstrap
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
* `.container`
* `.container-fluid`

## 网格
| 📱 Phone `<768px` | Pad `>=768px`    | 💻 Laptop `>=992px` | 🖥 Desktop `>=1200px` |
|:-----------------:|:----------------:|:------------------:|:---------------------:|
|      `col-xs-`    |   `col-sm-`      |     `col-md-`      |     `col-lg-`         |
|  `col-xs-offset`  | `col-sm-offset-` |  `col-md-offset-`  |   `col-lg-offset-`    |
|     `hidden-xs`   |    `hidden-sm`   |     `hidden-md`    |      `hidden-lg`      |
|    `visible-xs`   |   `visible-sm`   |    `visible-md`    |      `visible-lg`     |

* `.row`
* `.col-md-12`
* `.col-md-8`
* `.col-md-3`
* `.col-md-offset-1`
* `.col-sm-offset-0`

## 参考链接
* [Bootstrap 优站精选](http://expo.bootcss.com)
* http://getbootstrap.com
* 🇨🇳 http://www.bootcss.com
