---
layout: post
title: Python集成环境Anaconda及pygame安装
date: 2017-06-28
tags: 软件安装 
---

## 介绍

　　Anaconda是一个Python的分发版本，集成了很多关于Python'科学计算'的第三方库，并且能保证各库之间的版本保持一致（即库可以相互配合使用）。同时Anaconda是分离式安装，安装在一个单独的目录，避免与现有安装发生冲突。Anaconda中的库可通过其在线存储库自动更新。Conda软件包管理程序可高效管理给版本库。
　　Anaconda安装流程很简单，作为一个小记录，以便以后查阅，同时在Anaconda中安装Python游戏开发库pygame。



### 目录

* [基础知识](#change-dir)
* [判断语句](#download-soft)
* [循环语句](#tar-package)

### <a name="change-dir"></a>选择软件安装目录

/usr/local下一般是你安装软件的哈哈哈哈目录，这个目录就相当于在windows下的programefiles这个目录

/opt这个目录是一些大型软件的安装目录，或者是一些服务程序的安装目录
```
# mkdir /usr/local
# cd /usr/local
```

### <a name="download-soft"></a>下载软件

1、下载地址：http://www.sublimetext.com/3

*提示：Ubuntu 64 bit - also available as a **tarball** for other Linux distributions.*一定要下载**tarball**~~

2、命令行下载
```
wget http://c758482.r82.cf2.rackcdn.com/sublime_text_3_build_3126_x64.tar.bz2
```
*提示：请及时更新下载地址。*

### <a name="tar-package"></a>解压软件包
```
tar jxvf sublime_text_3_build_3126_x64.tar.bz2
```

<br>
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [Python集成环境Anaconda及pygame安装](http://zhoudingning.cn/2017/06/python_anaconda_and_pygame/)   

