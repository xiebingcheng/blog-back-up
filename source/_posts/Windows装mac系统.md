---
title: Windows装mac系统(虚拟机方法)
date: 2017-04-08 21:12:07
tags: [mac,os x,windows]
---
穷鬼没钱买mac,但是现在又需要mac系统,安装特定的软件.只好找个虚拟机安装mac的系统了.

这里找到两个博文, 重点是跟着博文1做,然后博文2辅助.

[博文1](http://blog.csdn.net/hamber_bao/article/details/51335834)

[博文2](http://www.jianshu.com/p/d2da6dd8cdb3)

首先跟着博文1来做: 博文1说的vmware workstation和VM12(VMware-player),其实是一个东西,一个是收费版的,另一个是简化版没收费的.

然后,跟着博文1做的时候,我遇见了大概3个报错,一个是 机器弹窗报错 "二进制错误" , 这个解决方法是: 进bios--将 Inter Virtuailization Technology 设置成enabled .(但是要注意,有些电脑的cpu不支持虚拟化,所以开不了,只能选择放弃安装mac的系统.可以用cpu-z 这个软件来测试一下,是否有此功能,查看方法是cpu选项的Instructions有VT-x,这个项,说明此电脑支持开启虚拟.)

第二个错是 
	
	锁定文件失败

	打开磁盘"E:\MAC\OS X 10.11.vmdk"或它所依赖的
	某个快照磁盘。

	模块"Disk"启动失败。

	未能启动虚拟机。

解决方法是:找到VM根目录(就是mac系统的根目录)，搜索.lck文件，全部删除，重启虚拟机即可.

第三个错误是 和博文一说的一样, 就是 "不可恢复错误:(vcpu-0)" 

解决方法和博文的一样即可. 找到根文件下的 OS X xx.xx.vmx,用记事本打开,在smc.present = “TRUE”后面，手动添加一句smc.version = 0。

然后安装好的虚拟机里的mac系统后,设置os x 系统按照博文2来就行,然后记住安装博文2最后那里提到的,VMware Tools

先弹出os x 的光盘,然后在虚拟机软件管理项目选项卡,安装VMware Tools,然后就行了.

	