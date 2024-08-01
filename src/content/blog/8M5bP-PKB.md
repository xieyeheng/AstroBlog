---
title: CSP初赛复习
author: xieyeheng
pubDatetime: 2023-09-02T04:06:31Z
slug: csp-chusai-fuxi
featured: false
draft: false
tags:
  - 学习
description:
  没写完，不想写了
---

# 1.哈夫曼编码

通过字符以及其对应出现的频率建立哈夫曼树。每次选择出现频率最小的两个字符合并为一个单元，直到全部合并。

例如有字符集 ${a,b,c,d,e}$，其每个字符对应的出现频率为 ${20%,10%,30%,15%,25%}$，则它的哈夫曼树长这样：
![](https://florr.cloud/post-images/1693629166893.png)

将树的左节点标记为 $1$，右节点标记为 $0$（其实反过来或标记为其他数字都行），然后就可以用一个10 串来表示每一个字符啦。例如 $e$ 是 $110$，$d$ 是 $11110$。