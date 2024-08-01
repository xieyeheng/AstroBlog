---
title: AT_abc322_c题解
author: xieyeheng
pubDatetime: 2023-10-05T04:06:31Z
slug: AT-abc322-c-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  AT_abc322_c题解
---

# 题意

AtCoder 王国举行为期 $N$ 天的节日活动。在其中的 $M$ 天，即 $A_1$ 天、$A_2$ 天、$\dots$ 天、$A_M$ 天，将燃放烟花。可以保证的是，烟花将在节日的最后一天燃放。(换句话说，$A_M=N$ 是有保证的）。

求每个 $i=1,2,\dots,N$ 的解。

- 从第 $i$ 天开始，第 $i$ 天或以后的第几天会首次燃放烟花？如果在 $i$ 日燃放烟花爆竹，则视为 $0$ 天后。

# 思路

如果某一天的值为 $-1$，表示这一天没有烟火表演，那么它将被设置为它后面一天的值加 $1$，表示离下一次烟火表演还有多少天。

# 代码

```python
N, M = map(int, input().split())
A = list(map(int, input().split()))

days_until_firework = [-1] * N

for day in A:
    days_until_firework[day - 1] = 0

for i in range(N - 2, -1, -1):
    if days_until_firework[i] == -1:
        days_until_firework[i] = days_until_firework[i + 1] + 1

for i in range(N):
    print(days_until_firework[i])


```
