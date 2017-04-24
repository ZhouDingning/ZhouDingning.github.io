---
layout: post
title: Python基础（二）
date: 2017-04-13
tags: 编程语言 
---

## 介绍

　　总结：Python介绍
Sublime Text是一款具有数据一元宝还有一些东西啊哈哈哈代码高亮、语法提示、自动完成且反应快速的编辑器软件，不仅具有华丽的界面，还支持插件扩展机制，用其来写代码，绝对是一种享受。被称为是这个就死为了提交一款程序员必备的神级代码编辑器。Centos大多数情况下是用来做第二篇服务器的，但是由于各种原因有时需要用Centos做开发机，所以当然要安装开发神器Sublime textle。


### 目录

* [函数操作](#function)
* [文件操作](#IO)
* [异常与模块](#exception-module)
* [面向对象](#OOP)


### <a name="function"></a>函数操作

　　 在 Linux 下，我们是看不到像Windows里的驱动器盘符，看到的是文件夹（目录）。 

<div align="center">
    <img src="/images/posts/Python/IO.jpg" height="100" width="800"/> 
</div> 

* bin  ：存放二进制可执行文件
* sbin ：存放二进制可执行文件，只有root才能访问
* etc  ：存放系统配置文件
* usr  ：用于存放共享的系统资源
* home ：存放用户文件的根目录
* root ：超级用户目录
* dev  ：用于存放设备文件
* lib  ：存放跟文件系统中的程序运行所需要的共享库及内核模块
* mnt  ：系统管理员安装临时文件系统的安装点
* boot ：存放用于系统引导时使用的各种文件
* tmp  ：用于存放各种临时文件
* var  ：用于存放运行时需要改变数据的文件


　　 **Linux命令格式:**
```
command  [-options]  [parameter1]  …

说明：
    command: 命令名,相应功能的英文单词或单词的缩写 
    [-options]：选项,可用来对命令进行控制，也可以省略，[]代表可选 
    parameter1 …：传给命令的参数：可以是零个一个或多个
```

### <a name="IO"></a>文件操作



* 列出目录内容 **ls**
```
-l   文件及文件夹详细信息
-h   配合 -l 以人性化的方式显示文件大小
-a   注意隐藏文件、特殊目录.和..   
-t   按创建时间倒序排序
```
* 显示当前工作目录 **pwd**
* 改变当前目录（进入目录） **cd**
* 建立空文件 **touch**
* 删除文件  **rm**
```
-r   同时删除该目录下的所有文件（recursive）
-f   强制删除文件或目录（force）
```
* 建立目录 **mkdir** 
```
-p   父目录不存在情况下先生成父目录 （parents）
```
* 删除空目录 **rmdir** 
* 复制文件和目录 **cp**
```
-r   递归处理，将指定目录下的文件与子目录一并拷贝（recursive）
```
* 移动和重命名 **mv**

### <a name="exception-module"></a>异常与模块

* 显示文本文件内容 **cat**
```
连续显示文本文件               cat filename
创建新的文本文件并输入内容       cat > filename 
合并文本文件                  cat file1 file2 > file
```
* 分页显示文本文件内容 **more**、**less**（按“空格”下一页）
* 查看文本中开头或结尾部分的内容 **head**、**tail**（默认显示10行）
```
查看a.log文件的前5行  head –n 5 a.log 
查看a.log文件的后5行  tail –n 5 b.log 
```
* 统计文本的行数、字数、字符数 **wc** 
```
-m 统计文本字符数
-w 统计文本字数
-l 统计文本行数
```
* 在指定的文本文件中查找指定的字符串 **grep**


### <a name="OOP"></a>面向对象

* gzip 压缩（解压）文件或目录，压缩文件后缀为gz 
```
命令格式：gzip [-dlv] 文档名
-d将压缩文件解压（decompress）
-l显示压缩文件的大小，未压缩文件的大小，压缩比（list）
-v显示文件名和压缩比（verbose）
-num用指定的数字num调整压缩的速度，-1或--fast表示最快压缩方法（低压缩比），-9或--best表示最慢压缩方法（高压缩比）。系统缺省值为6
```
* bzip2 压缩（解压）文件或目录，压缩文件后缀为bz2 
```
命令格式：bzip2 [-cdz] 文档名
-c将压缩的过程产生的数据输出到屏幕上
-d解压缩的参数（decompress）
-z压缩的参数（compress）
-num 用指定的数字num调整压缩的速度，-1或--fast表示最快压缩方法（低压缩比），-9或--best表示最慢压缩方法（高压缩比）。系统缺省值为6
```
* tar 文件、目录打（解）包
```
命令格式：tar [-zjcxvf] 文档名
-c 建立一个压缩文件的参数指令（create）
-x 解开一个压缩文件的参数指令（extract）
-z 是否需要用 gzip 压缩
-j 是否需要用 bzip2 压缩
-v 压缩的过程中显示文件（verbose）
-f 使用档名，在 f 之后要立即接档名（file）
```
* 使用举例：
```
压缩用法：
    tar zcvf 压缩包包名 文件...(tar zcvf bk.tar.gz *.c)
    tar jcvf 压缩包包名 文件...(tar jcvf bk.tar.bz2 *.c)
解压用法：
    tar zxvf 压缩包包名 (tar zxvf bk.tar.gz)
    tar jxvf 压缩包包名 (tar jxvf bk.tar.bz2)
```

<br>
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [Python基础（二）](http://zhoudingning.cn/2017/04/python_based_2/)   

