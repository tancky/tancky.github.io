---
title: 那些年我们一起踩过的坑——CSS中的命名及书写建议
tags: css
categories: html/css
---


今天来谈一谈我之前踩过的CSS坑之命名问题，相信很多跟我一样最开始学习CSS的时候都不知道怎样命名，有的起名字直接就是a，b，c，d（至少我初学的时候真的这么干过），更有甚者也会用汉语拼音来命名（例如这样：toubu，neirong，dibu等等），这些命名都是非常不好的习惯，在碰到很多复杂的页面布局时，这样命名会使自己不知所措，找一个class找很久都找不到，非常影响工（xue）作（xi）效率。<!--more-->经过我的多番搜寻与总结下，写了这篇博文。
## 为什么需要命名规范？

 > 合理、科学地对CSS代码命名,能够精简CSS代码,提高代码的开发效率,方便在日常工作中对网站进行维护与修改.遵循W3C所规定的语义化标准。

## 命名的基本标准

 - 类名使用小写字母，以中划线/下划线分隔
```html
<div class="header"></div>

```

 - id采用驼峰式命名且尽量少用
```html
 <div id="myDialog"></div>

```
 - 尽量不用拼音
```html
 <div id="pinyin"></div>

```
 - 尽量不缩写，除非一看就能懂的单词
```html
 <div class="fl"></div>     //fr即float: right;

```

 - 禁用通配符，影响性能



## CSS中的书写顺序

- 位置属性(position, display, float等)
- 大小(width, height, padding, margin)
- 文字系列(font系列, line-height, letter-spacing, color text-align等)
- 背景(background, border等)
- 其他(animation, transition等)

```html
 .box{
   position:relative;
   width:100px;
   height:100px;
   font-size:14px;
   text-align:center;
   background-color:#ccc;
 }

```

## 常用的class命名规范

 - 页面结构区
 
    容器: container
　　页头：header
　　内容：content/container
　　页面主体：main
　　页尾：footer
　　导航：nav
　　侧栏：sidebar
　　栏目：column
　　页面外围控制整体佈局宽度：wrapper
　　左右中：left right center

 - 导航

    导航：nav
　　主导航：mainnav
　　子导航：subnav
　　顶导航：topnav
　　边导航：sidebar
　　左导航：leftsidebar
　　右导航：rightsidebar
　　菜单：menu
　　子菜单：submenu
　　标题: title
　　摘要: summary

 - 功能区

    标志：logo
　　广告：banner
　　登陆：login
　　登录条：loginbar
　　注册：register
　　搜索：search
　　功能区：shop
　　标题：title
　　加入：joinus
　　状态：status
　　按钮：btn
　　滚动：scroll
　　标籤页：tab
　　文章列表：list
　　提示信息：msg
　　当前的: current
　　小技巧：tips
　　图标: icon
　　注释：note
　　指南：guild
　　服务：service
　　热点：hot
　　新闻：news
　　下载：download
　　投票：vote
　　合作伙伴：partner
　　友情链接：link
　　版权：copyright

 - CSS样式表文件命名

    全局：global.css
    
    全局样式为全站公用，为页面样式基础，页面中必须包含。
    
    结构：layout.css
    
    页面结构类型复杂，并且公用类型较多时使用。多用在首页级页面和产品类页面中。
    
    私有：style.css
    
    独立页面所使用的样式文件，页面中必须包含。
    
    模块 module.css
    
    产品类页面应用，将可复用类模块进行剥离后，可与其它样式配合使用。
    
    主题 themes.css
    
    实现换肤功能时应用。
    
    补丁 mend.css
    
    
        附图一张，加深记忆！
        
![CSS命名](http://i1.piimg.com/567571/4a295fce95d87fd6.png)

## 简单规则

 

 - 以中划线连接，如.item-img
 - 使用两个中划线表示特殊化，如.item-img.item-img--small表示在.item-img的基础上特殊化
 - 状态类直接使用单词，参考上面的关键词，如.active, .checked
 - 图标以icon-为前缀（字体图标采用.icon-font.i-name方式命名）。
 - 模块采用关键词命名，如.slide, .modal, .tips, .-        tabs，特殊化采用上面两个中划线表示，如.imgslide--full, .modal--pay, .tips--up, .tabs--simple
 - js操作的类统一加上js-前缀
 - 不要超过四个class组合使用，如.a.b.c.d
 

## 结语
好了，以上就是常用的css命名规则了，其实说白了规则就是"人如其名"，稍微懂点英语就知道只不过就是把网页中相对应的地方以英文的方式来命名，毕竟我们都是用英文来写代码的！写代码其实也可以帮助提升自己的英语水平的，一举两得，何乐而不为呢？
 
