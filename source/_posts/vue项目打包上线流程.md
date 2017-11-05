---
title: vue项目打包上线流程
tags: Vue.js
categories: JavaScript
---


 自己写的Vue项目终于大致完成了，由于没有买域名和服务器，但是项目要上线。思来想去发现github上可以直接用创建个人项目的上线演示，这给我带来了极大的便利，在维护源码的同时还能生成项目主页可供在线预览。简直美滋滋。<!--more-->但是由于第一次用这玩意儿，花费了我整整一天的时间，期间出现了各种问题，但俗话说得好：功夫不负有心人，终于在晚上把他给上线了，哈哈哈。
 
Github给用户提供了运行静态页面的地址，如何展示个人项目的静态页面？以下是创建项目主页的关键：

> gh-pages分支

> 访问地址：[github用户名].github.io/[项目仓库名]，如：tancky5.github.io/vue-acfun（不要脸的把自己的项目贴了上来哈哈）

生成项目主页首先是将想要展示的静态页面推送的Github个人项目仓库的gh-pages分支下，然后通过上述的访问形式访问。

至于如何使用git提交到github上这里我就直接忽略了，有兴趣的可以自己去网上看教程，一找一大堆。

由于我是使用vue-cli脚手架搭建的项目，所以代码压缩打包只需要npm run build一样就可以了，接下来才是关键!!!

第一步： 在github上点击你的项目进去之后点击settings

![项目](http://i4.piimg.com/1949/931e3f36070f9f95.png)

第二步： 找到github-pages 切换到gh-pages分支，然后点击save(保存),就会生成如图所示的链接，这个链接就是你的项目预览地址

![项目](http://i4.piimg.com/1949/74e5832ad5fdc34e.png)

第三步：在主分支master下run build打包代码（一定要先在master分支下build）,然后切换到gh-pages分支 

1. git checkout -b gh-pages


2. 在gh-pages再次执行 npm run build命令

3. 将dist目录下的所有文件夹推送至远程仓库的gh-pages分支，执行以下命令：

```
//强制添加dist文件夹，因为.gitignore文件中定义了忽略该文件
git add -f dist

//提交到本地暂存区
git commit -m 'Initial the page of project'

//部署dist目录下的代码
git subtree push --prefix dist origin gh-pages
```

此时打开刚才的链接就可以浏览自己的项目了，当然需要等那么一小会儿，毕竟页面需要加载时间。


虽然看着上面的流程很简单，其实真正自己上线的时候一个不小心就会有一堆错误，尤其是要先在master分支下build一次，然后切换到gh-pages分支下再build一次,否则的话，自己去试试就知道了，这是个深坑，多么痛的领悟！！！
