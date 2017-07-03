# BrowserSync 自动同步刷新页面

[BrowserSync](https://www.browsersync.io/) 可以在多个设备的浏览器上实现同步刷新页面，可以显著地提高页面开发效率。

## 前置条件
* 命令行工具
* Node.js 和 npm

具体下载地址和安装方法请查看【前端开发工具.md】

💡 如果你在中国大陆，建议先运行以下命令让 npm 使用阿里提供的镜像。
```bash
npm config set registry https://registry.npm.taobao.org
```

## 安装
```bash
$ npm install -g browser-sync
```

## 启动
⚠️ 此处假设你开发的是静态网页。

首先执行 `cd` 命令进入项目文件夹，如 `Code/Github/var`
```bash
$ cd Code/Github/var
```
执行命令 `browser-sync start --server --files .`
```bash
$ browser-sync start --server --files .
[BS] Access URLs:
 -------------------------------------
       Local: http://localhost:3000
    External: http://192.168.1.20:3000
 -------------------------------------
          UI: http://localhost:3001
 UI External: http://192.168.1.20:3001
 -------------------------------------
[BS] Serving files from: ./
[BS] Watching files...
```
运行命令后，BrowserSync 会自动打开一个浏览器页面访问 http://localhost:3000 。  
移动设备（在同一网络下，如家里 WIFI）, 可以访问 `External: http://192.......:3000` 处提供的具体地址访问页面。

## 关闭 BrowserSync
使用完毕后，在命令行界面按 Control + C 关闭 BrowserSync。

## 参考链接
* https://www.browsersync.io


