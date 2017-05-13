---
title: vue2.0学习之旅
date: 2017-03-22 20:46:09
tags: [vue,vue2,javascript]
---
贴几个有关的vue网站.

[vue中文官网](https://cn.vuejs.org/)

[vue源码](https:github.com/vuejs/vue)

[vue官方论坛](https://forum.vuejs.org)

[vue官方工具](https://github.com/vuejs)

[vue中文社区](http://www.vue-js.com/)

安装vue-cli 

	npm install vue-cli -g
	
	vue init webpack  //在要创建的文件夹下执行命令
	
	npm install //安装依赖
	
	npm run dev //在localhost中启动测试服务器
	
	npm run build //生成上线目录

vue标签的属性和条件渲染

	v-bind动态的绑定标签属性 简写: :
	
	使用v-bind是可以绑定class和内联的样式
	
	使用v-if,v-show,v-else进行条件渲染
	
	其中v-if是删除元素,直接从文档流里面删除,v-show删除元素,并不会删除文档流.

单文件组件

	文本渲染-v-html,{{}},v-text

事件绑定

	v-on @是简写, 在methods里事件绑定

表单数据模型双向绑定

	v-model
