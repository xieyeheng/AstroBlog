---
title: SP 19164题解
author: xieyeheng
pubDatetime: 2023-05-12T04:06:31Z
slug: sp-18164-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 18164题解
---

# 题意

给定 $n,k,m$，求 $n×k^t \leq m$ 时，$t$ 的最大值。

# 思路

对于这种给定幂的底数求幂的指数的题，我们可以想到用 `log` 这个方便而快捷的函数来解决。

`log` 函数有一个参数，作用是返回参数的 [自然对数](https://baike.baidu.com/item/%E8%87%AA%E7%84%B6%E5%AF%B9%E6%95%B0/270475) （即以 $e$ 为底的对数）。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
long long f(long long n,long long k,long long m){
	if (m<n){
		return 0;
	}
	return floor(log(m/n)/log(k));
}
int main(){
	int p;
	cin>>p;
	for (int i=1;i<=p;i++){
		long long n,k,m;
		cin>>n>>k>>m;
		cout<<f(n,k,m)<<endl;
	}
	return 0;
}
```
[![Page Views Count](https://badges.toozhao.com/badges/01H0858G0QRKT2GZF16H2M6KAV/green.svg)](https://badges.toozhao.com/stats/01H0858G0QRKT2GZF16H2M6KAV "Get your own page views count badge on badges.toozhao.com")

