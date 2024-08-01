---
title: 区间dp
author: xieyeheng
pubDatetime: 2023-07-11T04:06:31Z
slug: qv-jian-dp
featured: false
draft: false
tags:
  - 学习
description:
  dp 的笔记
---

# 方法

+ 合并：即将两个或多个部分进行整合，当然也可以反过来；

+ 特征：能将问题分解为能两两合并的形式；

+ 求解：对整个问题设最优值，枚举合并点，将问题分解为左右两个部分，最后合并两个部分的最优值得到原问题的最优值。

# 例题

[P1775 石子合并（弱化版）](https://www.luogu.com.cn/problem/P1775)

[P1880 [NOI1995] 石子合并](https://www.luogu.com.cn/problem/P1880)

[P1063 [NOIP2006 提高组] 能量项链](https://www.luogu.com.cn/problem/P1063)

# 要点

+ 记得初始化 $dp$ 数组

+ 在做类似 [P1775 石子合并（弱化版）](https://www.luogu.com.cn/problem/P1775) 和 [P1880 [NOI1995] 石子合并](https://www.luogu.com.cn/problem/P1880) 考虑好是链还是环。如果是环，要化成链

+ 拆分区间时要找好拆分点的边界

+ 模型变化/边界差别/计算方法