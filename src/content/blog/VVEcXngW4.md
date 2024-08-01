---
title: SP 1440题解
author: xieyeheng
pubDatetime: 2023-10-05T04:06:31Z
slug: sp-1440-tijie
featured: false
draft: false
tags:
  - 题解
description:
  SP 1440题解
---

# 题意

给出 $\arctan(\frac{1}{a})=\arctan(\frac{1}{b})+\arctan(\frac{1}{c})$ 中的 $a$，求 $b+c$ 的最小值。

# 思路

等式两边同时同取 $\tan$ 值，得到 $\frac{1}{a}=\frac{b+c}{b \times c-1}$，整理可得 $\frac{(b \times c-1)}{a}=b+c$，令 $y=b+c$，$b=x$，所以 $y=\frac{(y-x)\times x-1}{a}$，整理再求导可得 $y$ 在 $[a+1,2a]$ 区间单调递减，所以从 $2a$ 开始暴力即可

# 注意

+ 要开 64 位整数。

+ 代码长度限制 256 字节。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
long long t,a,n;
int main(){
	cin>>t;
	while (t--){
		cin>>n;
		a=n*2;
		while ((a*a+1)%(a-n)){
			a--;
		}
		cout<<(a*a+1)/(a-n)<<endl;
	}
	return 0;
}
```

~~说句闲话，这个是 [NOI 2001 Day1 T2](https://qoj.ac/contest/231/problem/4640) 的题在 SPOJ 上的搬运。~~