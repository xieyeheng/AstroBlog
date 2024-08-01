---
title: SP 12319题解
author: xieyeheng
pubDatetime: 2023-05-07T04:06:31Z
slug: sp-12319-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 12319题解
---

本题需要高精度，作为一个蒟蒻，我们考虑用 Python 解决。

Python 作为解释型语言，效率不如 C++，所以我们语言要用 Pypy 解释器，不然会超时。

然后我们需要注意 Python 用 `print` 输出后是自带换行的，我们要用 `end` 这个可选参数来控制换行

例子：

```python
#1
print("Hello",end=" ")
print("world")

#2
print("Hello")
print("world")
```
第一份代码的输出应为：
```
Hello world
```
第二位代码的输出为：
```
Hello
World
```


# 代码

```python
t=int(input())
#输入t
for i in range(t):
    #循环t次
    tmp=int(input())
    #输入数据
    if tmp%252==0:
        #能被252整除时输出Yes，end=" "把输出中最后的换行替换为空格
        print("Yes",end=" ")
    else:
        print("No",end=" ")
    if tmp%525==0:
        print("Yes")
    else:
        print("No")
 
```
[![Page Views Count](https://badges.toozhao.com/badges/01GZT5CJHKBYD03VDPQ3SM143J/green.svg)](https://badges.toozhao.com/stats/01GZT5CJHKBYD03VDPQ3SM143J "Get your own page views count badge on badges.toozhao.com")
