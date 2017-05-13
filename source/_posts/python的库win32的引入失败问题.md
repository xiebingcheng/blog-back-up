---
title: python的库win32的引入失败问题
date: 2017-01-13 16:43:33
tags: [python]
---
呜,心累.为了用这个win32库.

我用这个库,出现了一些问题.

1.这个库是.exe文件的形式,要安装对号入座的版本,比如你电脑的python是64位 2.7版本的.那这个win32也是要安装64位2.7版本的,我试了好多次,现在这个阶段不能用pip安装win32.

2.安装完成,版本正确,但是也是不能调用,特别在pyCharm这个编辑器上一直报错,找不到这个文件.
  
解决方法是: 是用 .pth 文件来实现。Python 在遍历已知的库文件目录过程中，如果见到一个 .pth 文件，就会将文件中所记录的路径加入到 sys.path 设置中，这样 .pth 文件说指明的库也就可以被 Python 运行环境找到。  
找到Python安装目录下的site-packages文件夹（$Python/Lib/site-packages）。

在该目录下创建一个PATH文件（*.pth），例如 MyModule.pth，打开新创建的文件，将你Python源文件所在的目录写入文件中。

比如我的saySomething.py文件的目录是E:/PythonSpace，PATH文件名为MyModule.pth。所以我的MyModule.pth的文件内容为：E:/PythonSpace。

除此之外，在高级设置中添加环境变量python/Lib/site-packages之后，重启下pycharm就可以在pycharm中 import win32api 了。

这些方法来自网络,各个博主的方法.我在把其中的方法提炼出来.在这里要谢谢各位博主帮忙.

(我用的是建一个.pth文件弄好的,现在pyCharm对于win32库没报错了.)