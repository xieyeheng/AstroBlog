---
title: SP 10676题解
author: xieyeheng
pubDatetime: 2023-06-10T04:06:31Z
slug: sp-10676-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 10676题解
---

# 题意

求长度为 $n$ 的 01 串有多少种组合方法。

# 思路

对于组合运算，我们可以理解为无顺序地，从 $m$ 个物体中中选出 $n$ 个物体进行排序，在数学中记作 $C_m^n$。

在这道题中，我们假定选择了 $k$ 个 $1$，则剩下的 $n-k$ 个字符都是 $0$，即 在 $k+1$ 的 $1$ 和 $1$ 的间隔中插空 $0$，所以它的组合数量表达式为 $C_{k+1}^{n-k}$。

对于 Python 语言，在 `math` 库中有一个函数叫 `math.comb()`，它可以计算组合数，所以我们就不用手打组合了。

# 代码

```python
import math
n=int(input())
ans=0
for k in range(0,n+1,1):
    ans+=math.comb(k+1,n-k)
print(ans)
```
