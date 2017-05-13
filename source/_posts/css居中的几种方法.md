---
title: css居中的几种方法
date: 2016-10-22 00:06:58
tags: [css]
---

以前在搜集了几种html样式居中的方法,参照了网络上各位大侠博主的博文,我现在也写一篇供以后的不时之需.

### 1.用margin+position来实现.

总所周知啦,margin:0 auto 经常用来实现水平居中,但是如果是margin:auto,并不能实现居中.  但是如果加上posttion的话..

	.center{
	margin:auto;
	posirion:absolute;
	top:0;left0;bottom:0;right:0;
	}

大虾说,这种用法优点在于:

1.支持跨浏览器，包括IE8-IE10.

2.无需其他特殊标记，CSS代码量少

3.支持百分比%属性值和min-/max-属性

4.只用这一个类可实现任何内容块居中

5.不论是否设置padding都可居中（在不使用box-sizing属性的前提下）

6.内容块可以被重绘。

7.完美支持图片居中。

但是记住这样的方法,必须声明高度.

### 2.用绝对定位和负边距

代码

	.box3{position:relative;}
	.box3 span{
           	position: absolute;
            width:100px;
            height: 50px;
            top:50%;
            left:50%;
            margin-left:-50px;
            margin-top:-25px;
            text-align: center;
        }

### 3.通过 display:inline-block

	.box{
  	  text-align:center;
  	  font-size:0;
	}
	.box span{
  	  vertical-align:middle;
  	  display:inline-block;
  	  font-size:16px;
	}
	.box:after{
  	  content:'';
  	  width:0;
	  height:100%;
	  display:inline-block;
	  vertical-align:middle;
	}

after是用来占位的..