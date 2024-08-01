---
title: SP 9494题解
author: xieyeheng
pubDatetime: 2023-06-23T04:06:31Z
slug: sp-9494-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 9494题解
---

# 思路

首先，这种题用常规方法做肯定会超时的，于是我们需要推导一下这个式子，找到规律。



$$Z_{n}+Z_{n-1}-2 Z_{n-2}$$
$$=\left(Z_{n}-Z_{n-2}\right)+\left(Z_{n-1}-Z_{n-2}\right)$$
$$=(S_{n}+Q_{n}-S_{n-1}-Q_{n-1})+(S_{n-1}+Q_{n-1}-S_{n-2}-Q_{n-2})$$
$$=S_{n}-S_{n-1}+S_{n-1}-S_{n-2}+Q_{n}-Q_{n-1}+Q_{n-1}-Q_{n-2}$$
$$=S_{n}-S_{n-2}+Q_{n}-Q_{n-2}$$
$$=n^{n}+n^{k}+2 \times(n-1)^{n-1}+2 \times(n-1)^{k}$$


规律找到后，我们发现直接计算乘方会超时，所以我们再写一个快速幂就行了。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
long long n,k;
const int MOD=1e7+7;
long long quickpow(long long a,long long b){
	long long ans=1;
	while (b){
		if (b&1){
			ans=ans*a%MOD;
		}
		a=a*a%MOD;
		b>>=1;
	}
	return ans;
}
int main(){
	while (scanf("%lld%lld",&n,&k) and (n or k)){
		long long ans=((quickpow(n-1,n-1)*2+
						quickpow(n-1,k)*2)%MOD+
						quickpow(n,k)+
						quickpow(n,n))%MOD;
		printf("%lld\n",ans);
	}
	return 0;
} 

```
