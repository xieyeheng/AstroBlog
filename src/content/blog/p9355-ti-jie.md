---
title: P9355题解
author: xieyeheng
pubDatetime: 2023-06-10T04:06:31Z
slug: p9355-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  P9355 题解
---

# 思路

给定两个相邻的格子 A 和 B，我们会发现无论是 A 比 B 先放还是 B 比 A 先放，都会有 $1$ 的得分值。手动模拟几个棋盘，我们会发现其实所有策略都是一样的，所以我们找规律就行。

# 代码


```python
t=int(input())
for i in range(t):
    [n,m]=list(map(int, input().split()))
    ans=(n-1)+(n*2-1)*(m-1)
    print(ans)
```
