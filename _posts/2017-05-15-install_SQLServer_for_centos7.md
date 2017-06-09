---
layout: post
title: Centos7下安装SQL Server
date: 2017-05-15
tags: 操作系统  
---

## 介绍

　　SQL Server数据库一般指Microsoft SQL Server，是windows生态系统的关系型数据库，其高度集成化，微软也提供了整套的软件方案，基本上一套Windows系统装下来就可以了。因此，不那么缺钱，但很缺IT人才的中小企业，会偏爱MS SQL Server 。例如，自建ERP系统、商业智能、垂直领域零售商、餐饮、事业单位等等。然而一般主流的服务器是Linux操作系统，在项目部署中就会遇到在Linux中安装SQL Server的问题，这篇博客就介绍一下在Centos7中安装SQL Server。

　　注：要求系统内存至少3250M，少一点就报错。。。



### 目录

* [下载SQL Server源](#download-sqlserver)
* [安装SQL Server](#insatll-sqlserver)
* [初始配置](#configuration)
* [查看状态](#view-status)
* [设置防火墙](#setup-firewall)
* [SSMS连接服务器上SQL Server](#remote-connection)


### <a name="download-sqlserver"></a>下载SQL Server源

```
# curl https://packages.microsoft.com/config/rhel/7/mssql-server.repo > /etc/yum.repos.d/mssql-server.repo
```
*提示：请及时更新下载地址。*

### <a name="insatll-sqlserver"></a>安装SQL Server

```
# yum install -y mssql-server
```

### <a name="configuration"></a>初始配置

1、是否要启动sql server服务，是否要在系统启动时启动sql server，输入：yes

2、设置sql server的系统管理员sa的密码，必须是强密码类型（即密码最少8个字符，由数字、字母数字和符号等组成）

```
# /opt/mssql/bin/mssql-conf setup
```

### <a name="view-status"></a>查看状态
```
# systemctl status mssql-server
```

### <a name="setup-firewall"></a>设置防火墙

1、开放1433端口
```
# firewall-cmd --zone=public --add-port=1433/tcp --permanent  
```

2、重启防火墙
```
# firewall-cmd --reload
```

### <a name="remote-connection"></a>SSMS连接服务器上SQL Server

在windows上用Microsoft SQL Server Management Studio（ssms）连接
```
1、服务器名称：192.168.239.128  （服务器IP）
2、登录名：sa
3、密码：123456sa.  （强密码类型）
```

<br>
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [Centos7下安装SQL Server](http://zhoudingning.cn/2017/05/install_SQLServer_for_centos7/)   

