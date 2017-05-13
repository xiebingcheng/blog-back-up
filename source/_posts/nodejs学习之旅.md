---
title: nodejs学习之旅
date: 2017-02-13 00:25:53
tags: [node,踩坑,javascript]
---
1.不需要重启就能看到更改node代码的效果(supervisor)

在使用node开发的时候,会因为频繁更改代码而导致node程序都要每次的手动重启,才能看到效果(因为node是直接获取内存的东西,不像php是直接重新加载.).使用supervisor 可以解决这个问题.

	npm install -g supervisor

运行

	supervisor --harmony app.js

2.关于node 的 -dev和没有-dev的区别

--save-dev 是你开发时候依赖的东西(测试环境下)，--save 是你发布之后还依赖的东西(上线时还需要的依赖)。

