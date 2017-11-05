---
title: vue-cli上线打包出现的图片路径解析问题
tags: Vue.js
categories: JavaScript
---



自己写的移动端项目（仿Acfun弹幕视频网）基本上已经搞定了，可是在npm run build打包上线时却出现了问题，关于图片资源路径解析的问题<!--more-->，在网上查了很久，终于找到了解决方案。

由于用的是vue-cli脚手架搭建的项目，所以图片默认的存放地址是src/assets/img下。

![地址信息](http://chuantu.biz/t5/133/1499920370x2071187492.png)

在开发过程中，大部分情况下都是用img标签来引用图片资源，like this：

![地址信息](http://chuantu.biz/t5/133/1499920513x2728328999.png)

or this:

![地址信息](http://chuantu.biz/t5/133/1499920622x2728328999.png)

如果所有的图片资源都是用img标签来引用的话，vue-cli在上线打包的时候路径解析不会出现问题亲测。但是如果用css的background-img来引用图片资源的话打包时候就会报错！！！ like this：

![地址信息](http://chuantu.biz/t5/133/1499920778x2728328999.png)

解决方案来了（来自stackoverflow）：

![地址信息](https://sfault-image.b0.upaiyun.com/218/085/218085424-5941fbc5785d3)

划重点：

1.在 config/index.js 中修改 assetsPublicPath 为 ./ （上线打包时需要更改的目录路径）

2.在 build/utils.js 中的 ExtractTextPlugin.extract 传入参数 publicPath: '../../'

只需以上两步，就能完美解决本地和服务器上资源url解析的问题。





  
  
  
  
  