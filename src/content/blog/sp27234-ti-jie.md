---
title: SP 27234题解
author: xieyeheng
pubDatetime: 2023-06-13T04:06:31Z
slug: sp-27234-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 27234题解
---

# 思路

这是一道递推的题目，坑点在于洛谷上的题面没有给出最后的答案需要答案对 $1000000007$。

![SPOJ上的题面](https://img1.imgtp.com/2023/06/22/6swsEUEl.png)

至于怎么递推呢？我们先手动算一下几个数对应的答案。

$2=2$

$3=3$

$5=3+2$

不难发现，我们想要知道一个数 $n$ 的累加方法，就要知道 $n-2$ 和 $n-3$ 的累加方法。若以 $ans_{i}$ 储存 $i$ 的累加方法，则有 $ans_{i}=ans_{i-2}+ans_{i-3}$。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
const int MAXN=1e6+10;
const int MOD=1e9+7;
int ans[MAXN],ask[MAXN],m=0;
long long t;
int main(){
	ans[1]=0,ans[2]=1,ans[3]=1;
	cin>>t;
	for (int i=1;i<=t;i++){
		cin>>ask[i];
		m=max(m,ask[i]);
	}
	for (int i=4;i<=m;i++){
		ans[i]=(ans[i-3]+ans[i-2])%MOD;
	}
	for (int i=1;i<=t;i++){
		cout<<ans[ask[i]]<<endl;
	}
	return 0;
}
```
