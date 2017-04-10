---
layout: post
title: Centos下安装sublime text3
date: 2017-04-07
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

　　图像大多排列为 3-D 阵列，具体指 高度、宽度 和 颜色通道。例如，如果你使用电脑截屏，它将首先转换成一个 3-D 数组，然后压缩它为 '.jpeg' 或 '.png' 文件格式。

### <a name="use-soft"></a>命令行下直接运行

让我们从官方定义开始.

　　“`TensorFlow` 是一个开源软件库，用于使用数据流图进行数值计算。图中的节点表示数学运算，而图边表示在它们之间传递的多维数据阵列（也称为张量）。 灵活的架构允许您使用单一 API 将计算部署到桌面、服务器或移动设备中的一个或多个的 CPU 或 GPU 中。


### <a name="desktop-soft"></a>创建桌面快捷方式

　　每个库都有自己的“实现细节”，即一种写其遵循其编码范例的方式。 例如，当实现 scikit-learn 时，首先创建所需算法的对象，然后在训练和测试集上构建一个模型获得预测，如下所示：

```python

# define hyperparamters of ML algorithm
clf = svm.SVC(gamma=0.001, C=100.)
# train 
clf.fit(X, y)
# test 
clf.predict(X_test)
```

### <a name="open-soft"></a>打开软件

*注意：我们可以使用不同的神经网络体系结构来解决这个问题，但是为了简单起见，我们在深入实施中讨论 `前馈多层感知器`。*

让我们记住对神经网络的了解。

<br>
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [centos下安装sublime text3](http://zhoudingning.cn/2017/04/install_sublimeText_for_centos/)   

