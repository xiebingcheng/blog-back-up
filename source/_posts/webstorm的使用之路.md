---
title: webstorm的使用之路
date: 2016-10-25 16:05:30
tags: [webstorm,IDE,编辑器]
---
代码缩写补全:  
div>ul>li*3 + tab键

	<div>
	    <ul>
	        <li></li>
	        <li></li>
	        <li></li>
	    </ul>
	</div>

其中,不光是>,还有 +(代表同级元素) ^(代表向上爬升一级) 还有挂号()

挂号的用法: (header>div>ul>li*3)+footer

	<header>
	    <div>
	        <ul>
	            <li></li>
	            <li></li>
	            <li></li>
	        </ul>
	    </div>
	</header>
	<footer></footer>

还有生成id # 类. 等等,  
{} p{设有},就是<p>设有</p>

生成无意义的文字 lorem   lorem80生成80个无意义的文字  

在css文件也可以用.

以上是Emmet的语法

webstorm快捷键

多光标的选择:    
快捷键 alt + 鼠标左键拖动 //相同列的情况下使用  
非相同键的情况: alt + 鼠标左键想点哪里就哪里

本地修改历史:  
右键点击要查看的代码页面+local History 选择show History

代码格式化: ctrl + alt +L

代码行移动alt+shift+向上或者先下箭头

跳转目标行：ctrl + g

按着shift浮在图片上方可以看到图片的预览

Shift + F6 重命名(变量,标签名等)

我觉得最好用的一点是, webstorm有个大纲,可以查看html js的结构,大纲按钮在webstorm的左下角的那个类似电脑触摸板的图标,点击就会出现.

