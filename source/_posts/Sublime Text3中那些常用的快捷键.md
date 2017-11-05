---
title: Sublime Text3中那些常用的快捷键
tags: Sublime Text
categories: Sublime Text
---
  学习前端时间也不短了，记得最开始学HTML/css的时候是通过《Head First HTML与CSS》这本书开始接触前端的，快递包裹拆开的时候整个人都懵逼了。好厚的一本书，整整700多页，对于我这种直到大学毕业了还没有好好的看过书的人来说简直是场灾难！不过幸好之前有在知乎了解到这本书虽然很厚，但是绝大部分都是以图文的形式展示出来的，所以看起来不会那么的吃力让人想睡觉。后来边看边跟着敲代码，当时的我还傻不拉几的用的windows系统自带的记事本，每天重复得敲着<html><head></head></html>...等等，竟然没有很厌烦的感觉，反而乐此不疲，也许这就是在自学前端的过程中所能给我带来的最大的快乐吧，看到自己敲的代码在浏览器中呈现出来，那种感觉只有亲身经历过才会懂！
  
  
直到我接触了sublime Text编辑器也就是今天这篇文章的重点，我就深深的爱上了他！<!--more-->熟练掌握各种快捷键，可以给我们日常工作中带来极大的便利，节约时间成本，把精力专心地放在项目上。那么首先我们来看看他有哪些优点！
> Sublime Text：一款具有代码高亮、语法提示、自动完成且反应快速的编辑器软件，不仅具有华丽的界面，还支持插件扩展机制，用她来写代码，绝对是一种享受。相比于难于上手的Vim，浮肿沉重的Eclipse，VS，即便体积轻巧迅速启动的Editplus、Notepad++，在SublimeText面前大略显失色，无疑这款性感无比的编辑器是Coding和Writing最佳的选择，没有之一。

## 最常用的快捷键（以windows系统为例）
    


### 命令面板

- 双击界面后按下Ctrl+shift+p即可调用命令面板像这样

![命令面板](http://i1.piimg.com/567571/90259d0897d885ba.png)
        
- 我们可以输入Package Control安装各种插件  【首推Emmet插件】(PS:sublime text编辑器支持模糊匹配，例如输入Package Control，那么只需要输入pctl即可匹配到该命令，如下图所示)

![命令面板](http://i1.piimg.com/567571/1ae879010b551e56.png)        
        
- 也可以输入html，css，JavaScript等来改变要使用的语言环境

![命令面板](http://i1.piimg.com/567571/4e6777f367263ad8.png)    

### 多行游标

 - Ctrl+H：查找替换
 
 - Ctrl+D 选词 （选中某个文本后，反复按快捷键即可选中下一个相同的文本同时编辑）
 
 - Ctrl+K Ctrl+D 跳过当前选择，选择下一个
 
 - Alt+F3 选择所有与光标所在单词相同的单词
  
 - 按住shift键，然后按住鼠标右键向下拖动，也可产生多行游标
 
![命令面板](http://p1.bpimg.com/567571/3db00a73f0251227.png) 

    第二个图为连续按了5次Ctrl+D后的结果， 也可以直接按Alt+F3！
![命令面板](http://p1.bpimg.com/567571/50f2bb5cf95611f1.png)


### 搜索，撤销，反撤销
 - Ctrl+F 搜索 （搜索当前文档中相对应的字符串，搜索到的字符串以高亮显示）

![命令面板](http://p1.bpimg.com/567571/d67923e3b1cbcdff.png) 

 - Ctrl+Z 撤销 （撤销上一步的操作，可重复按键）
 

 - Ctrl+Y 取消撤销（与之相反）
 
![命令面板](http://p1.bpimg.com/567571/046f325568dd5853.png) 

    按下Crtl+Z后

![命令面板](http://p1.bpimg.com/567571/1fd1819f78ae94b4.png) 
 
### 标签页切换        
- Ctrl+Tab （当前窗口中的标签页切换）
 
![命令面板](http://p1.bqimg.com/567571/5956d7336b9b60f2.png) 

    切换后效果   
    
![命令面板](http://p1.bqimg.com/567571/906b7f5ebb6e0813.png) 
### 删除整行
- Ctrl+Shift+K （删除整行）
 
![命令面板](http://p1.bqimg.com/567571/c578a0f4ab4d93e2.png) 
            
    删除后效果   


![命令面板](http://p1.bqimg.com/567571/2265fe38920c723c.png) 



## 学以致用

### 如何快速搭建一个HTML文档

- Ctrl+N 

- Ctrl+S   保存页面 
![命令面板](http://p1.bqimg.com/567571/44936a881c3538af.png)


- Ctrl+shift+p  调用命令面板输入，输入HTML调用语言

![命令面板](http://i1.piimg.com/567571/50a48a9b34374fc3.png)

- 编辑区输入！号

![命令面板](http://i1.piimg.com/567571/97155fb46a7cfdfb.png)

- Ctrl+E 

![命令面板](http://i1.piimg.com/567571/d93d37845fda2ef9.png)

- Ctrl+P 输入#body回车即可跳转至body标签 

![命令面板](http://i1.piimg.com/567571/6e621d3ad422c47b.png)

![命令面板](http://i1.piimg.com/567571/1ca8efa598e2d074.png)

- Ctrl+Enter 在当前行下添加一行 

- ctrl+shirt+enter 在当前行上方添加一行（与之相反）

![命令面板](http://i1.piimg.com/567571/2f728a1ca18eba45.png)

- (ul>.item \$*10{content} )   （ > 号生成子元素 ，\$ 产生序号，{ }产生内容 ）


![命令面板](http://i1.piimg.com/567571/db6d17920f20c790.png)

- Ctrl+E 

![命令面板](http://i1.piimg.com/567571/056f235dfff6c6eb.png)

- Ctrl+] 增加缩进 

- Ctrl+[ 减小缩进

![命令面板](http://i1.piimg.com/567571/fc1c6e3b10018421.png)

- 光标点击需要多选的位置


![命令面板](http://p1.bqimg.com/567571/8fd0f3152d2abd5c.png)

- Alt+F3  全选


![命令面板](http://p1.bqimg.com/567571/0944cf6800892e76.png)

- 输入h3{}，然后Ctrl+E（注：Ctrl+E也可以用来闭合元素标签）


![命令面板](http://p1.bqimg.com/567571/ff68d5f0f59d03ed.png)


![命令面板](http://p1.bqimg.com/567571/56a0a1aa9a8c1e28.png)

## 结语

好了，以上就是在开发过程中常见的一些快捷键，希望可以通过图文并茂的方式可以更好的帮助记忆（PS：受head first 系列图书的影响...），其实这里面也有很多我自己也没用过的快捷键，以后没事儿的时候多来看看，再敲代码的时候就可以更轻松了哈哈哈，这样极大限度的摆脱鼠标的困扰，两耳不闻窗外事，一心只去敲代码！
Fighting！！！
