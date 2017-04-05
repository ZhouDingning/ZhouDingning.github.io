---
layout: post
title: Linux基本操作（二）
date: 2017-04-03
tags: 操作系统  
---

## 介绍

　　在上一篇文章[Linux基本操作（一）](http://zhoudingning。github.io/2017/04/Linux_based_1/)中，介绍了Linux操作系统以及其结构，并就常用的命令如文件与目录操作、文本文件操作等做了相关介绍，同时介绍了Linux中强大的文本编辑器Vim。在这篇文章中，将继续介绍Linux系统的相关操作。


### 目录

* [用户与权限管理](#users)
* [网络配置](#network)
* [web应用安装](#webAPP)


### <a name="users"></a>用户与权限管理

**配置文件**
* 保存用户信息的文件：/etc/passwd
```
account:password:UID:GID:GECOS:directory:shell
```
* 保存密码的文件：/etc/shadow
* 保存用户组的文件：/etc/group
* 保存用户组密码的文件：/etc/gshadow
* 用户配置文件：/etc/default/useradd

**用户管理**
* 添加用户 **useradd**
```
-u 指定用户ID（uid）
-g 指定所属的组名（gid）
-G 指定多个组，用逗号“，”分开（Groups）
-c 用户描述（comment）
-e 失效时间（expire date）
添加密码: passwd 用户名
```
* 修改用户命令：**usermod**
```
-l 修改用户名 （login）usermod -l a b（b改为a）
-g 添加组 usermod -g sys tom
-G 添加多个组 usermod -G sys,root tom
-L 锁定用户账号密码（Lock）
-U 解锁用户账号（Unlock）
```
* 删除用户命令：**userdel**
```
-r 删除账号时同时删除目录（remove）
```
* 添加组：**groupadd**
```
-g 指定gid
```
* 修改组：**groupmod**
```
-n 更改组名（new group）
```
* 删除组：**groupdel**
* 显示用户所属组：**groups** 

**权限管理**
* 三种基本权限
```
r 读权限（read）
w 写权限（write）
x 执行权限（execute）
```
<div align="center">
    <img src="/images/posts/Linux/root.jpg" height="140" width="600"/>
</div>

　　第1位：文件类型（d 目录，- 普通文件，l 链接文件）

　　第2-4位：所属用户权限，用u（user）表示

　　第5-7位：所属组权限，用g（group）表示

　　第8-10位：其他用户权限，用o（other）表示

　　第2-10位：表示所有的权限，用a（all）表示

　　完整信息：一个文件，所属用户具有读写执行权限；所属组的用户有读写权限，没有执行权限；其他用户只有读权限

* 更改用户权限 **chmod**
```
参数：-R 下面的文件和子目录做相同权限操作（Recursive递归的）
        例如：chmod  u+x  a.txt
用数字来表示权限（r=4，w=2，x=1，-=0）
        例如：chmod  750  b.txt
rwx用二进制表示是111，十进制4+2+1=7
r-x用二进制表示是101，十进制4+0+1=5
```

### <a name="network"></a>网络配置
**VMWare三种工作模式**

　　VMWare提供了三种工作模式，它们是bridged(桥接模式)、NAT(网络地址转换模式)和host-only(主机模式)。要想在网络管理和维护中合理应用它们，你就应该先了解一下这三种工作模式。

* bridged(桥接模式)

　　在这种模式下，VMWare虚拟出来的操作系统就像是局域网中的一台独立的主机，它可以访问网内任何一台机器。在桥接模式下，你需要手工为虚拟系统配置IP地址、子网掩码，而且还要和宿主机器处于同一网段，这样虚拟系统才能和宿主机器进行通信。同时，由于这个虚拟系统是局域网中的一个独立的主机系统，那么就可以手工配置它的TCP/IP配置信息，以实现通过局域网的网关或路由器访问互联网。
使用桥接模式的虚拟系统和宿主机器的关系，就像连接在同一个Hub上的两台电脑。想让它们相互通讯，你就需要为虚拟系统配置IP地址和子网掩码，否则就无法通信。
如果你想利用VMWare在局域网内新建一个虚拟服务器，为局域网用户提供网络服务，就应该选择桥接模式。

* host-only(主机模式)

　　在某些特殊的网络调试环境中，要求将真实环境和虚拟环境隔离开，这时你就可采用host-only模式。在host-only模式中，所有的虚拟系统是可以相互通信的，但虚拟系统和真实的网络是被隔离开的。
提示:在host-only模式下，虚拟系统和宿主机器系统是可以相互通信的，相当于这两台机器通过双绞线互连。
在host-only模式下，虚拟系统的TCP/IP配置信息(如IP地址、网关地址、DNS服务器等)，都是由VMnet1(host-only)虚拟网络的DHCP服务器来动态分配的。
如果你想利用VMWare创建一个与网内其他机器相隔离的虚拟系统，进行某些特殊的网络调试工作，可以选择host-only模式。

* NAT(网络地址转换模式)

　　使用NAT模式，就是让虚拟系统借助NAT(网络地址转换)功能，通过宿主机器所在的网络来访问公网。也就是说，使用NAT模式可以实现在虚拟系统里访问互联网。NAT模式下的虚拟系统的TCP/IP配置信息是由VMnet8(NAT)虚拟网络的DHCP服务器提供的，无法进行手工修改，因此虚拟系统也就无法和本局域网中的其他真实主机进行通讯。采用NAT模式最大的优势是虚拟系统接入互联网非常简单，你不需要进行任何其他的配置，只需要宿主机器能访问互联网即可。

　　如果你想利用VMWare安装一个新的虚拟系统，在虚拟系统中不用进行任何手工配置就能直接访问互联网，建议你采用NAT模式。

　　**提示**:以上所提到的NAT模式下的VMnet8虚拟网络，host-only模式下的VMnet1虚拟网络，以及bridged模式下的VMnet0虚拟网络，都是由VMWare虚拟机自动配置而生成的。VMnet8和VMnet 1提供DHCP服务，VMnet0虚拟网络则不提供。


**设置静态IP**

步骤如下：
* （1）选择虚拟软件的网络类型为host-only 
* （2）进入vm的虚拟网络编辑器修改IP网段
* （3）修改虚拟网络VMnet1的IP地址
* （4）配置linux虚拟机

　　　a)  修改主机名
```
命令行下敲入：  vim /etc/sysconfig/network  
设置HOSTNAME名称
```
　　　b)  修改IP
```
命令行下敲入：vim /etc/sysconfig/network-scripts/ifcfg-eth0
如图所示设置
```
<div align="center">
    <img src="/images/posts/Linux/ip.jpg" height="200" width="500"/>
</div>
　　
　c)  修改主机名和IP映射关系
```
命令行敲入： vim /etc/hosts
添加一行：192.168.8.251  xxx
```

**防火墙管理**

* 防火墙开放端口
```
敲入命令：vim /etc/sysconfig/iptables 
让防火墙重启：/etc/init.d/iptables restart
```
* 临时开启或关闭防火墙
```
开启：service iptables start
关闭：service iptables stop
判断是否开启：service iptables status
```
* 永久开启或关闭防火墙
```
开启：chkconfig iptables on
关闭：chkconfig iptables off
```

### <a name="webAPP"></a>web应用安装

**远程登陆与文件传输工具**
* 文件上传：SFTP协议  软件：FileZilla_3.7.3_win32
* 远程登陆：SSH   软件：SecureCRT

**RPM 命令使用**

　　（RedHat软件包管理工具）的缩写，这一文件格式名称虽然打上了RedHat的标志，但是其原始设计理念是开放式的，现在包括RedHat、CentOS、SUSE等Linux的分发版本都有采用，可以算是公认的行业标准了。RPM文件在Linux系统中的安装最为简便。
```
rpm的常用参数
i：  安装应用程序（install）
e：  卸载应用程序（erase）
vh： 显示安装进度；（verbose hash） 
U：  升级软件包；（update） 
qa： 显示所有已安装软件包（query all）
结合grep命令使用，例：rpm -qa | grep 'mysql' 
例子：rpm  -ivh  gcc-c++-4.4.7-3.el6.x86_64.rpm
```

**YUM命令使用**

　　Yum（全称为 Yellow dog Updater, Modified）是一个在Fedora和RedHat以及SUSE、CentOS中的Shell前端软件包管理器。基於RPM包管理，能够从指定的服务器自动下载RPM包并且安装，可以自动处理依赖性关系，并且一次安装所有依赖的软件包，无须繁琐地一次次下载、安装。
* 查看已安装： yum list installed
* 卸载已安装： yum -y remove java-1.7.0-openjdk
* 测试网络是否通畅： ping www.baidu.com
* 搜索yum库： yum -y list java
* 安装： yum -y install java-1.7.0-openjdk

<br>
转载请注明：[周定宁的博客](http://zhoudingning。github.io) » [Linux基本操作（一）](http://zhoudingning。github.io/2017/04/Linux_based_2/)  
