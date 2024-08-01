---
title: 数位 DP
author: xieyeheng
pubDatetime: 2023-07-12T04:06:31Z
slug: shuwei-dp
featured: false
draft: false
tags:
  - 学习
description:
  数位 DP
---

# 特点

求某个区间 $[L,R]$内，满足某个性质的数的个数。

# 技巧

1. 类似前缀和思想，**转化**为：$[0,R]$ ~ $[0,L-1]$求解。
2. 从高位到低位填数，**分类讨论**
