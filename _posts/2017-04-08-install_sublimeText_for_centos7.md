---
layout: post
title: Centos7下安装sublime text3
date: 2017-04-08
tags: 操作系统  
---

## 介绍

　　Sublime Text是一款具有代码高亮、语法提示、自动完成且反应快速的编辑器软件，不仅具有华丽的界面，还支持插件扩展机制，用其来写代码，绝对是一种享受。被称为是一款程序员必备的神级代码编辑器。Centos大多数情况下是用来做服务器的，但是由于各种原因有时需要用Centos做开发机，所以当然要安装开发神器Sublime textle。


### 目录

* [选择软件安装目录](#change-dir)
* [下载软件](#download-soft)
* [解压软件包](#tar-package)
* [命令行下直接运行](#use-soft)
* [创建桌面快捷方式](#desktop-soft)
* [打开软件](#open-soft)


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
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [Centos7下安装sublime text3](http://zhoudingning.cn/2017/04/install_sublimeText_for_centos7/)   

