---
title: 状压 DP
author: xieyeheng
pubDatetime: 2023-07-13T04:06:31Z
slug: zhuangya-dp
featured: false
draft: false
tags:
  - 笔记
description:
  dp 笔记
---

# 状态压缩

1. 用 **二进制** 表示状态，用 **十进制** 存储状态。
2. 用位运算筛选出合法状态。
3. 用位运算判断状态转移的条件。
4. 计算时每个类累加上一行的兼容类。

# 例题

[P1896 [SCOI2005] 互不侵犯](https://www.luogu.com.cn/problem/P1896)

[P1879 [USACO06NOV] Corn Fields G](https://www.luogu.com.cn/problem/P1879)

