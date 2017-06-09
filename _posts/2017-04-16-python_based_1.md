---
layout: post
title: Python基础（一）
date: 2017-04-16
tags: 编程语言 
---

## 介绍

<div align="center">
    <img src="/images/posts/Python/python0.jpg" height="122" width="372"/> 
</div> 

　　Python 是一个高层次的结合了解释性、编译性、互动性和面向对象的脚本语言。

　　Python 简单、易学，其设计具有很强的可读性，高度的可移植性、可扩展性和可嵌入性。

　　Python 是免费、开源的，这造就了其具有丰富和强大的库。

　　Python 采用强制缩进的方式来规范代码，使得代码具有极佳的可读性。

　　　　　　***人生苦短，我用Python***
<div align="center">
    <img src="/images/posts/Python/python.jpg" height="268" width="390"/> 
</div> 

### 目录

* [基础知识](#basic-knowledge)
* [判断、循环语句](#if-while)

### <a name="basic-knowledge"></a>基础知识

**1、注释**

　　通过用自己熟悉的语言，在程序中对某些代码进行标注说明，这就是注释的作用，能够大大增强程序的可读性。

* 单行注释
```python
# 单行注释，一般为功能说明
print('hello world')
```

* 多行注释
```python
'''
	多行注释，可以写很多行的功能说明
	功能输入：XX
	功能过程：BP网络
	功能输出：YY
'''
    print("YY")
```

* 中文注释 ( *如果直接在程序中用到了中文，直接运行输出，程序会出错* )
```python
#coding=utf-8
print("人生苦短，我用Python")
```

**2、变量及类型**

　　变量的作用，就是用来存储数据的
* 类型 
```python
Number（数字）：int、long、float、complex（复数）
Bool（布尔）：True、Float
String（字符串）
List（列表）
Tuple（元组）
Dictionary（字典）
```

**3、输入与输出**

* 输入
```
python2.x
	获取到string类型：raw_input("请输入：")
	获取到表达式结果：input("请输入：")
python3.x
	获取到string类型：input("请输入：")
```
* 输出
```
python2.x
	print "输出为：" , num
python3.x
	print("输出为：" , num)
格式化输出(2.x与3.x均可)
	如：print("运算结果为：%d" %(num))
```

**4、运算符**

* 算术运算符
```python
+(加)、 -(减)、 *(乘)、 /(除)、 %(取余)、 **(幂)、 // (取整除)
```
* 复合赋值运算符
```
+=、 -=、 *=、 /=、 %=、 **=、 //=
```
* 关系运算符
```
==(相等)、 !=(不相等)、 <>=(不相等)、 >(大于)、 <(小于)、 >=(大于等于)、 <=(小于等于)
```
* 逻辑运算符
```
and(与)、 or(或)、 not(非)
```

### <a name="if-while"></a>判断、循环语句

* if-elif-else判断
```python
if 条件1:
    满足条件1要做的事情
    ...
elif 条件2:
	满足条件2时要做的事情
    ...
else:
	不满足条件1和2时要做的事情
    ...
```

* while循环
```
while 条件:
	条件满足时，做的事情1
	条件满足时，做的事情2
	...
```
* for循环（遍历集合）
```
for temp in list:
	要做的事情
```
* 中止循环
```
break：用来结束整个循环
continue：用来结束本次循环，紧接着执行下一次的循环
```

<br>
转载请注明：[周定宁的博客](http://zhoudingning.cn) » [Python基础（一）](http://zhoudingning.cn/2017/04/python_based_1/)   

