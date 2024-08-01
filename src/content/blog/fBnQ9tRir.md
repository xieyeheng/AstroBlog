---
title: Nim问题
author: xieyeheng
pubDatetime: 2024-07-31T04:06:31Z
slug: nim-question
featured: false
draft: false
tags:
  - 学习
description:
  一些关于 Nim 问题的笔记
---

# 前置

[例题](https://www.luogu.com.cn/problem/P2197)

大意：给定 $n$ 堆石子和每堆石子是数量，两个人轮流取，每次取的数量无上限，至少取一个，求是否存在先手必胜策略。

# 思路

## 考虑两堆石子的情况

### 两堆石子数量不相等

先手玩家先取石子多的那堆，使两堆石子数量相等，然后模仿后手玩家操作即可必胜。**此时存在先手必胜策略**

### 两堆石子数量不相等

先手玩家取石子后，后手玩家模仿先手玩家操作即可。**此时不存在先手必胜策略**。

## 考虑三堆及更多石子的情况

启发：似乎与堆的数量与石子数量的奇偶性有关。
例题：考虑一个四堆的 Nim 问题，四堆石子数量分别为 $7,9,12,15$。
想法：二进制表示石子数量，得到：

|  | $2^3=8$ | $2^2=4$ | $2^1=2$ | $2^0=1$ |
| -----------: | -----------: | -----------: | -----------: | -----------: |
| 堆7 | 0 | 1 | 1 | 1 |
| 堆9 | 1 | 0 | 0 | 1 |
| 堆12 | 1 | 1 | 0 | 0 |
| 堆15 | 1 | 1 | 1 | 1 |

# 结论

当 $n$ 堆石子的数量异或和等于 $0$ 时，先手必胜，否则先手必败。