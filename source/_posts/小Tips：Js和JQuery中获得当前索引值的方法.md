---
title: 小Tips：Js和JQuery中获得当前索引值的方法
tags: JavaScript
categories: JavaScript
---

自从用了Jquery库以后，感觉写Js代码没有那么繁琐了，之前自己用JQuery仿京东首页做了一个轮播图（就差无缝切换了...），代码量仅仅用了几十行，后来打算用原生JS写一遍的时候就悲剧了。<!--more-->上百行的代码量，而且JQuery用多了，自己竟然连获取原生JS中的当前索引值都不会了，还是要好好补补原生JS，基础很重要！基础很重要！基础很重要！重要的事情说三遍！所以，今天就记录下曾经踩过的坑，长个记性！
在一些常见的特效里比如轮播图，下拉列表，Tab切换里都会用到循环遍历取得当前索引值并添加事件的方法，在JS中取得当前索引的方法是：
``` HTML
<body>
    <ul id="test">
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
        <li>6</li>
        <li>7</li>
        <li>8</li>
    </ul>
</body>
```

``` JavaScript
window.onload=function(){                        //当页面全部加载完毕后执行
        var oUl=document.getElementById("test"), //获取父元素ul
            oli=oUl.getElementsByTagName("li");  //获取所有的子元素li
        for(var i=0; i<oli.length; i++){         //循环遍历每一个li元素
                                                
            oli[i].index=i;                      //重点来了（Js中获取当前索引值的方法）
            
            oli[i].onclick=function(){           //给当前元素添加点击事件
               alert(this.index);                //输出当前的索引值
            }
        }
}


```

以上就是原生JS中获取当前索引的方法，其实不难就那么一行代码，虽然当时困扰了我很久....接下来就来写JQuery中的方法，这个就更简单啦！

``` JavaScript
 $(function () {
    $("#test li").on('click', function() {
			var me=$(this);         //将当前元素存入名为me的变量里

			index=me.index();              //获取当前的索引值
			alert（index）；               //输出当前的索引值
        }
}
```

看到没，JQuery代码就是这么简单，因为JQuery中提供了index() 方法，该方法返回指定元素相对于其他指定元素的索引值。

写个笔记，给自己提个醒，同样的坑不能掉下去两次了！！！





