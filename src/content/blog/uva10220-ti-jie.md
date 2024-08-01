---
title: UVA 10220题解
author: xieyeheng
pubDatetime: 2023-06-10T04:06:31Z
slug: uva-10220-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  UVA 10220题解
---

这题数据范围为 $1 \le \left | n ! \right | \le 2^{31} - 1$，很明显需要一个高精度。所以我们可以想到用 Python 解决该问题。

# 思路

求出 $n!$ 后将其作为一个字符串遍历一遍，累计记录答案，最后输出即可。

我们可以使用 `math` 标准库中的 `factorial` 函数来计算阶乘。该函数接受一个参数，返回该参数的阶乘。

但是该函数不是万能的，它在接受过大的参数时会抛出 `OverflowError` 错误，例如：

![](https://picdl.sunbangyan.cn/2023/05/22/xpef4e.png)

# 代码

```python
import math
# 导入math标准模块，便于计算阶乘
while True:
    # 死循环读入数字
    try:
        n=int(input())
        # 读入数字，并试图捕获错误
    except:
        exit(0)
        # 有错误（输入结束时），终止程序
    x=math.factorial(n)
    # 计算 n 的阶乘
    ans=0
    x=str(x)
    # 将 x 转换为字符串
    for i in x:
        # 遍历 x 的每个字符
        ans+=int(i)
        # 更新答案
    print(ans)

```
