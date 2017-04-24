---
layout: post
title: Python基础（一）
date: 2017-04-11
tags: 编程语言 
---

## 介绍

　　Python 是一个高层次的结合了解释性、编译性、互动性和面向对象的脚本语言。

　　Python 简单、易学，其设计具有很强的可读性，高度的可移植性、可扩展性和可嵌入性。

　　Python 是免费、开源的，这造就了其具有丰富和强大的库。

　　Python 采用强制缩进的方式来规范代码，使得代码具有极佳的可读性。

　　　　　　***人生苦短，我用Python***

### 目录

* [基础知识](#basic-knowledge)
* [判断、循环语句](#if-while)
* [字符串和列表](#string-list)
* [字典和元组](#dictionary-tuple)
* [进制及数据类型转换](#system-dataType)


### <a name="basic-knowledge"></a>基础知识

　　 在 Linux 下，我们是看不到像Windows里的驱动器盘符，看到的是文件夹（目录）。 

<div align="center">
    <img src="/images/posts/Python/if-while.jpg" height="100" width="800"/> 
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

### <a name="if-while"></a>判断、循环语句



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

### <a name="string-list"></a>字符串和列表

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


### <a name="dictionary-tuple"></a>字典和元组

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

### <a name="system-dataType"></a>进制及数据类型转换

* system-dataType简介

　　 vi / system-dataType是Unix / Linux上最常用的文本编辑器而且功能非常强大。只有命令，没有菜单。

<div align="center">
    <img src="/images/posts/Linux/system-dataType.jpg" height="200" width="400"/> 
</div> 
* 插入命令
```
i   在光标前插入
I   在光标当前行开始插入
a   在光标后插入
A   在光标当前行末尾插入
o   在光标当前行的下一行插入新行
O   在光标当前行的上一行插入新行
```
* 定位命令
```
:set nu     显示行号
:set nonu   取消行号
gg          到文本的第一行
G           到文本的最后一行
:n          到文本的第n行
```
* 删除命令
```
x         删除光标所在处字符
nx        删除光标所在处后的n个字符
dd        删除光标所在行。ndd删除n行
dG        删除光标所在行到末尾行的所以内容
D         删除光标所在处到行尾的内容
:n1,n2 d  删除指定范围的行
```
* 替换和取消命令
```
u        取消上一步操作
Ctrl+r   返回到undo之前
r        替换光标所在处的字符
R        从光标所在处开始替换，按Esc键结束
```
* 可视模式
```
v            进入字符可视模式
V/Shift + v  进入行可视模式
Ctrl + v     进入块可视模式
（1）选定文本块，使用v进入可视模式；移动光标键选定内容
（2）复制选定块到缓冲区，用y；复制整行，用yy
（3）剪切选定块到缓冲区，用d；剪切整行用dd
（4）粘贴缓冲区中的内容，用p
```
* 常用快捷键
```
Shift+zz   保存退出
“:wq”       保存退出
“:q!”      不保存退出
```

<br>
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [Python基础（一）](http://zhoudingning.cn/2017/04/python_based_1/)   

