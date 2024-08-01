---
title: SP 2881题解
author: xieyeheng
pubDatetime: 2023-04-30T04:06:31Z
slug: sp-2881-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 2881题解
---

## 思路
我们使用到了 `defaultdict` 数据类型来进行字符串的计数，同时也用了列表来记录字符串和结果。

我们使用一个循环，当输入的 $n$ 和 $m$ 都为零时结束程序。在处理每个测试用例时，记录新出现的字符串来计数，最后更新结果。

## 步骤

+ 用 $len$ 表示不同的序列个数，用 $cnt$ 表示每种序列的出现次数，用 $ans$ 数组记录出现次数分别为一到 $n$ 的某个序列的个数。

+ 创建一个长度为 $n$ 加一的 $ans$ 列表，并将序列的长度最大值设为一个自定义的常量 $mxn$ 后创建一个长度为 $mxn$ 的列表，全部初始化为空字符串。

+ 循环读入 $n$ 个序列。

+ 对于每个序列，首先用 `strip()` 函数去掉字符串左右的空格，再判断当前序列是否在字典 $cnt$ 中，如果不在，则将其存入列表，序列数加一。

+ 不论当前序列是否在字典 $cnt$ 中，字典 $cnt$ 中当前序列的计数器加一。

+ 循环一到 $len$ 加一，遍历所有序列。 $ans$ 列表的第 $cnt$ 的 $dna_{i}$ 个元素加一，表示序列 $dna_{i}$ 出现的次数为 $cnt$ 的 $dna_{i}$ 项。

+ 遍历并输出。

## 代码

代码如下：

```python
from collections import defaultdict
# 导入collections 中的defaultdict函数
mxn = int(1e5+10)

while True:
    n, m = [int(x) for x in input().split()]
    # 输入n和m
    if n == 0 and m == 0:
        # 输入结束
        break
    
    len = 0
    # 虽然len是一个内置函数，但是用它当变量名也不是不行
    cnt = defaultdict(int)
    # 建一个defaultdict
    ans = [0] * (n+1)
    # 开一个长度为n+1的ans列表存答案
    dna = [''] * mxn
    # 开一个很长的列表来存dna序列
    
    #下面的内容代码外面有讲
    for i in range(1, n+1):
        ins = input().strip()
        if cnt[ins] == 0:
            len += 1
            dna[len] = ins
        cnt[ins] += 1
    
    for i in range(1, len+1):
        ans[cnt[dna[i]]] += 1
    
    for i in range(1, n+1):
        print(ans[i])

```
[![Page Views Count](https://badges.toozhao.com/badges/01GZ821CRB9KRH5C4EG14RT04P/blue.svg)](https://badges.toozhao.com/stats/01GZ821CRB9KRH5C4EG14RT04P "Get your own page views count badge on badges.toozhao.com")