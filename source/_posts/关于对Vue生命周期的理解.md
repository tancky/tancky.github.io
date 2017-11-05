
---
title: 关于对Vue生命周期的理解
tags: Vue.js
categories: JavaScript
---



----------


最近一直在写一个Vue的单页SPA移动端项目，虽然遇到了很多问题，踩了不少的坑，但同时对Vue的学习与理解也更加深入了。在做项目的时候经常会分不清 created,mounted等钩子函数的用法，不知道应该何时运用，怎么运用。实际上只要搞懂了Vue的生命周期，就能‘运筹帷幄之中，决胜于千里之外了’。今天来谈一谈有关Vue生命周期的理解。<!--more-->（以最新的Vue2.0为基础）

> Vue实例有一个完整的生命周期，也就是从开始创建、初始化数据、编译模板、挂载Dom、渲染→更新→渲染、卸载等一系列过程，我们称这是Vue的生命周期。通俗说就是Vue实例从创建到销毁的过程，就是生命周期。

官方的图示

![Vue生命周期](https://cn.vuejs.org/images/lifecycle.png)

我最开始看这个图的时候也是一脸懵逼，不过没关系。通俗地来说，可以理解为人的一生从出生到死亡分别经历的不同阶段（胎儿，婴儿，少年，青年，中年，老年等），而这些阶段就是所谓的‘钩子’，利用这些钩子（即钩子函数）可以注册一些需要的方法，从而达到控制整个过程的目的。

结合代码来看一下

```
<!DOCTYPE html>
<html>
<head>
    <title></title>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/vue/2.1.3/vue.js"></script>
</head>
<body>

<div id="app">
     <p>{{ message }}</p>
</div>

<script type="text/javascript">
    
  var app = new Vue({
      el: '#app',
      data: {
          message : "xuxiao is boy" 
      },
       beforeCreate: function () {
                console.group('beforeCreate 创建前状态===============》');
               console.log("%c%s", "color:red" , "el     : " + this.$el); //undefined
               console.log("%c%s", "color:red","data   : " + this.$data); //undefined 
               console.log("%c%s", "color:red","message: " + this.message)  
        },
        created: function () {
            console.group('created 创建完毕状态===============》');
            console.log("%c%s", "color:red","el     : " + this.$el); //undefined
               console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化 
               console.log("%c%s", "color:red","message: " + this.message); //已被初始化
        },
        beforeMount: function () {
            console.group('beforeMount 挂载前状态===============》');
            console.log("%c%s", "color:red","el     : " + (this.$el)); //已被初始化
            console.log(this.$el);
               console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化  
               console.log("%c%s", "color:red","message: " + this.message); //已被初始化  
        },
        mounted: function () {
            console.group('mounted 挂载结束状态===============》');
            console.log("%c%s", "color:red","el     : " + this.$el); //已被初始化
            console.log(this.$el);    
               console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化
               console.log("%c%s", "color:red","message: " + this.message); //已被初始化 
        },
        beforeUpdate: function () {
            console.group('beforeUpdate 更新前状态===============》');
            console.log("%c%s", "color:red","el     : " + this.$el);
            console.log(this.$el);   
               console.log("%c%s", "color:red","data   : " + this.$data); 
               console.log("%c%s", "color:red","message: " + this.message); 
        },
        updated: function () {
            console.group('updated 更新完成状态===============》');
            console.log("%c%s", "color:red","el     : " + this.$el);
            console.log(this.$el); 
               console.log("%c%s", "color:red","data   : " + this.$data); 
               console.log("%c%s", "color:red","message: " + this.message); 
        },
        beforeDestroy: function () {
            console.group('beforeDestroy 销毁前状态===============》');
            console.log("%c%s", "color:red","el     : " + this.$el);
            console.log(this.$el);    
               console.log("%c%s", "color:red","data   : " + this.$data); 
               console.log("%c%s", "color:red","message: " + this.message); 
        },
        destroyed: function () {
            console.group('destroyed 销毁完成状态===============》');
            console.log("%c%s", "color:red","el     : " + this.$el);
            console.log(this.$el);  
               console.log("%c%s", "color:red","data   : " + this.$data); 
               console.log("%c%s", "color:red","message: " + this.message)
        }
    })
</script>
</body>
</html>
```
![组件创建之前状态](https://sfault-image.b0.upaiyun.com/130/248/1302481017-586cddaf83195)
## 一.beforeCreate 
console.log(this.\$data), undefined，说明：
组件实例被创建，组件属性计算之前，如data属性等

应用：可以在这加个loading事件 

## 二.created
注意触发vue的created事件以后,this便指向vue实例(划重点！！！)
console.log(this.\$data),已经将data数据打印出来，说明：

1.组件实例创建完成，属性已经绑定，但DOM还未生成，\$el属性还不存在
2.在实例创建之后同步调用。此时实例已经结束解析选项，这意味着已建立：数据绑定，计算属性，方法，watcher/事件回调。
3.但是还没有开始 DOM 编译，$el 还不存在,但是实例存在,即this.\$data存在,可打印出来 。

应用：在这结束loading，还做一些初始化，实现函数自执行 
## 三.beforeMount
在模板编译，挂载开始之前被调用,在标红处，我们能发现el还是 {{message}}，这里就是应用的 Virtual DOM（虚拟Dom）技术，先把坑占住了。到后面mounted挂载的时候再把值渲染进去。
## 四.mounted
1.模板编译、挂载之后不保证组件已在document中
2.在编译结束后调用。此时所有的指令已生效，因而数据的变化将触发 DOM 更新。但是不担保 $el 已插入文档。

应用：mounted阶段做ajax，或者配合路由钩子做一些事情;此时DOM已经获取到，可以对DOM进行操作。

## 五.beforeUpdate
```
app.message= 'yes !! I do';
```
![组件更新状态](https://sfault-image.b0.upaiyun.com/970/506/970506402-586cdf5fb1fe1)

1.数据更新时调用，发生在虚拟 DOM 重新渲染和打补丁之前。
2.你可以在这个钩子中进一步地更改状态，这不会触发附加的重渲染过程。
3.该钩子在服务器端渲染期间不被调用。

## 六.updated
由于数据更改导致的虚拟 DOM 重新渲染和打补丁，在这之后会调用该钩子。当这个钩子被调用时，组件 DOM 已经更新，所以你现在可以执行依赖于 DOM 的操作。
然而在大多数情况下，你应该避免在此期间更改状态，因为这可能会导致更新无限循环。

## 七.beforeDestroy
```
app.$destroy();
```

![组件销毁状态](https://sfault-image.b0.upaiyun.com/396/155/3961550519-586ce0cb13de2)

1.组件销毁前触发
2.触发方式,在console里面打myVue.$destroy();
3.在开始销毁实例时调用。此时实例仍然有功能。

应用：beforeDestory 你确认删除XX吗？
## 八.destroyed
1.触发方式,在console里面打myVue.$destroy();其中myVue.\$destroy(true)是删除DOM节点,会触发detached函数,但是实例仍然存在
2.在实例被销毁之后调用。此时所有的绑定和实例的指令已经解绑，注意是解绑不是销毁,所有的子实例也已经被销毁。
应用：destoryed当前组件已被删除，清空相关内容

有关于销毁，暂时还不是很清楚。我们在console里执行下命令对 vue实例进行销毁。销毁完成后，我们再重新改变message的值，vue不再对此动作进行响应了。但是原先生成的dom元素还存在，可以这么理解，执行了destroy操作，后续就不再受vue控制了。





  
  
  
  
  