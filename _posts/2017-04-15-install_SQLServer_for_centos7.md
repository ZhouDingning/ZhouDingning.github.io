---
layout: post
title: Centos7下安装SQL Server
date: 2017-04-15
tags: 操作系统  
---

## 介绍

　　SQL Server数据库一般指Microsoft SQL Server，是windows生态系统的关系型数据库，其高度集成化，微软也提供了整套的软件方案，基本上一套Windows系统装下来就可以了。因此，不那么缺钱，但很缺IT人才的中小企业，会偏爱MS SQL Server 。例如，自建ERP系统、商业智能、垂直领域零售商、餐饮、事业单位等等。然而一般主流的服务器是Linux操作系统，在项目部署中就会遇到在Linux中安装SQL Server的问题，这篇博客就介绍一下在Centos7中安装SQL Server。注：要求系统内存至少3250M，少一点就报错。。。



### 目录

* [下载SQL Server源](#download-sqlserver)
* [安装SQL Server](#insatll-sqlserver)
* [初始配置](#configuration)
* [查看状态](#view-status)
* [设置防火墙](#setup-firewall)
* [SSMS连接服务器上SQL Server](#remote-connection)


### <a name="change-dir"></a>选择软件安装目录

/usr/local下一般是你安装软件的目录，这个目录就相当于在windows下的programefiles这个目录

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

### <a name="use-soft"></a>命令行下直接运行
```
# cd /usr/local/sublime_text_3
# ./sublime_text
```

### <a name="desktop-soft"></a>创建桌面快捷方式

1、复制文件
```
# cp /usr/local/sublime_text_3/sublime_text.desktop /usr/share/applications
```

2、更改配置文件
```
# vim /usr/share/applications/sublime_text.desktop

配置信息
[Desktop Entry]
Version=1.0
Type=Application
Name=Sublime Text
GenericName=Text Editor
Comment=Sophisticated text editor for code, markup and prose
Exec=/usr/local/sublime_text_3/sublime_text %F                   #修改路径
Terminal=false
MimeType=text/plain;
Icon=/usr/local/sublime_text_3/Icon/48x48/sublime-text.png       #修改路径
Categories=TextEditor;Development;
StartupNotify=true
Actions=Window;Document;

[Desktop Action Window]
Name=New Window
Exec=/usr/local/sublime_text_3/sublime_text -n                   #修改路径
OnlyShowIn=Unity;

[Desktop Action Document]
Name=New File
Exec=/usr/local/sublime_text/sublime_text_3 --command new_file   #修改路径
OnlyShowIn=Unity;
```

### <a name="open-soft"></a>打开软件

应用程序 >编程 > Sublime Text”右键”将此启动器添加到桌面”

*去掉更新提示：找到Preferences -> Settings-User（设置用户），找到倒数第三行的//"update_check": false, 把注释去掉*

<br>
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [Centos7下安装SQL Server](http://zhoudingning.cn/2017/04/install_SQLServer_for_centos7/)   

