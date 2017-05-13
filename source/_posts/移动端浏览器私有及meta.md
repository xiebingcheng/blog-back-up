---
title: 移动端浏览器私有及meta
date: 2016-10-30 15:51:06
tags: [javascript,浏览器]
---

项目中的一些浏览器私有meta

UC浏览器私有

全屏模式

	<meta name="full-screen" content="yes">

强制竖屏

	<meta name="screen-orientation" content="portrait">

强制横屏

	<meta name="screen-orientation" content="landscape">

应用模式

	<meta name="browsermode" content="application">

其它

针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓

	<meta name="HandheldFriendly" content="true">

微软的老式浏览器

	<meta name="MobileOptimized" content="320">

windows phone 点击无高光

	<meta name="msapplication-tap-highlight" content="no">

以后继续补充一些.