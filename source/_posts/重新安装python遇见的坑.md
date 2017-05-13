---
title: 重新安装python遇见的坑
date: 2017-01-13 13:01:58
tags: [python]
---
唉,我今天想要写一个python脚本,这个脚本需要调用Windows系统的aip.需要用到一个库,就是pywin32.  
然后,踩坑之旅就这样开始了..

我在下载这个pywin32的时候,发现我那时候下载的python2.7版本是32位操作系统的..我的天.那时候我真的是什么都不懂,乱下载.然后我是新手中的新手,根本用不出来32位和64位的有什么差别.  
但是这次我要调用系统aip.为了防止以后会有更多的坑,我毅然决然的选择重新安装python2.7版本.

然后我这次安装的是python2.7.12版本的.结果发现pip不能使用.而且是解决一个坑,又出现第二个坑,就是连环坑等着我去跳.下面我一个一个的说说,防止我以后如果还要重新安装python的时候,又忘记了.

1.用pip下载库的时候,报错:一段英文,大致意思是,pip的版本过低,比如是8.0.1版本的,他让你升级到9.0.0版本.  
解决方法是:去到python27的安装目录里,找到这个scripts文件夹,然后shift+右键打开窗口命令.输入指令: easy_install.exe pip==9.0.0(错误提示你升级到哪个版本,你就升级到哪个版本.)

2.pip下载库,继续报错,如果出现的错误提示英文中有 "error: Microsoft Visual C++ 10.0 is required (Unable to find vcvarsall.bat)." 之类的,而且还给了你一个网站,叫你去那边下载这个缺少的 c++库,你就去下载然后安装就可以了.网站(https://www.microsoft.com/en-us/download/details.aspx?id=44266)

3.对了,还有一个我认为也是比较重要的,还是记录一下吧. 在下载python然后安装的时候,对话框如图有这个选项的时候,记得一定要勾选上.pip和Add python.exe to Path ,勾第二个的意思是: 这样就可以不用手动去弄python的环境变量之类的了.
![python安装对话框](http://www.liaoxuefeng.com/files/attachments/0014222393965540081463bf8a9499094bdda24b6fdf2d6000)

------
2017.2.22 更新

4.我都无语了,今天不注意用360把我电脑上的python2.7删除了,我的电脑有两个版本,3的和2的版本,删除了一个..哭死..  
然后我下载继续安装,结果怎么都安装不了, 然后我看到对话框的提示,是说![提示框](https://pic3.zhimg.com/1f664204b90d921e725dc2cd3ff878e2_b.jpg)

说什么有一个东西不能安装,之类的.然后我百度了一下,说的是这样的结果.
[知乎的大神说的,安装时选择for me，不是for all users ，（我也没选择安装pip），我的已经成功安装。](https://www.zhihu.com/question/30733889)反正就是安装的第一个选项选择for me ,然后不选择安装pip就行了.
但是这样还是出了个问题,就是安装好的python2.7没有pip可以用,这个时候我又去百度了一下,结果有很多,然后我想起了之前第二条要更新pip的事,我就想着用 easy_install来安装pip就好了..结果..    
不安装pip的下,连easy_install都没有,所以要先下载easy_install先.
[下载easy_install的地址](https://pypi.python.org/pypi/ez_setup)
然后下载 ez_setup.py 到桌面后，按住键盘的 shift 键，右击鼠标，选中“在此处打开命令窗口”，进入 DOS 界面，输入命令：python ez_setup.py 就行了,easy_install安装好后,结合我上次写的第二条就可以安装pip了.(记住,pip最好安装最新版的,要不然python又提示你安装最新的pip了..[查看最新的pip版本](https://pypi.python.org/pypi/pip))    
想来想去,还是在贴一个大神的博文,安装pip的另一种方法吧,以备不时之需.. 这些坑踩到我都怕了,想想看是要换Mac了.. [http://blog.csdn.net/xsj_blog/article/details/52037609](http://blog.csdn.net/xsj_blog/article/details/52037609)