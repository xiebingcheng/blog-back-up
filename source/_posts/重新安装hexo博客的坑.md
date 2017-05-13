---
title: 重新安装hexo博客的坑
date: 2017-03-05 16:50:11
tags: [hexo,node,博客]
---
终于搞好了.几天前怪我手贱.想玩玩nodejs的版本管理工具,nvm.然后在我的电脑下(windows7 64位).把原来的node删除,安装了nvm管理node.结果..不知道为什么的,node的npm包安装不了.然后..就没有然后了, 接着连node都用不了了.在google下的很多方法都不能用后,于是我只好重装系统.

接着 hexo 搭建的博客也更新不了了.. 弄了半天 google了好久,终于搞定了.

不说多了,怕下次还会重装系统出现这样的问题,导致浪费时间.特此记录一下.

首先,以前没玩过hexo搭建博客的.可以参考一下下面两个博客,我是按照这两个博客弄的.但是技术日新月异,最好直接参照hexo官网,搭建..

[博客一](http://www.cylong.com/blog/2016/04/19/hexo-git/)

[博客二](http://hifor.net/2015/07/01/%E9%9B%B6%E5%9F%BA%E7%A1%80%E5%85%8D%E8%B4%B9%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2-hexo-github/)

下面这个才是真正的正文..

重装系统后,如果还想继续玩hexo搭建的博客.  
1.首先把原来的没重装系统前的博客的文件夹,直接复制里面的内容到你想要安装的新目录文件夹中.  
2._config.yml，theme/，source/，scaffolds/，package.json，.gitignore，是需要拷贝的留下来的.  
3..git/，node_modules/，public/，.deploy_git/，db.json文件需要删除。  
4.然后,删除好了以后, 用命令npm install 自动安装package.json的文件.  
5.输入下面这两个命令,获取你的用户名和邮箱(可以以后直接不要每次部署的时候每次都输入自己的名字了!)  

	git config --global user.name "YOUR NAME"
	git config --global user.email "YOUR EMAIL ADDRESS"
其中，YOUR NAME 是自己取的名字，YOUR EMAIL ADDRESS 是自己的 Github 邮箱。

6.关键的一点是,因为重装系统了,就没有git公钥了,所以要打开git bash
输入命令

	$ ssh-keygen -t rsa -C "youremail@example.com"  //后面换成你的github邮箱
然后一路按回车,完成后打开c盘.搜索 id_rsa.pub 这个文件,找到后,用随便哪个编辑器打开他.复制里面的内容,  
接着,我们去github官网登录账号后,
登陆GitHub，打开「Settings」->「SSH and GPG keys」，然后点击「new SSH key」，填上任意Title，在Key文本框里粘贴公钥id_rsa.pub文件的内容（千万不要粘贴成私钥了！），最后点击「Add SSH Key」，你就应该看到已经添加的Key。  
7.这回也是很重要的一点是:为了能用 hexo d 这个命令部署到github上面,需要安装

	npm install hexo-deployer-git --save

这回就大功告成了! 这回,重装系统或者换电脑了,也可以继续使用hexo更新博客了!

关于安装好hexo后,使用的一些命令:
新建md文件:

	hexo new 'my-first-blog' #创建一个md文件
启动服务器,查看本地效果

	hexo s //默认开在4000 端口 http://localhost:4000
上传到github的命令组,

	hexo clean  # 清除之前 public 文件夹的内容

生成静态的 public 文件夹，部署时候也是直接拷贝此文件夹里的文件。

	hexo g

部署到 Github 上，按照提示输入自己 Github 的用户名和密码。

	hexo d 
当然上面的 hexo g 和hexo d 命令可以合并成:

	hexo d --g #或者 hexo g --d
主要参考文献:
[知乎大神--skycrown 在答案的大概中间位置,android开发](https://www.zhihu.com/question/21193762)  
[多机更新 Hexo 博客](http://lowrank.science/Hexo-Migration/)