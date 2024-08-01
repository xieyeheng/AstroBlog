---
title: SP 5917题解
author: xieyeheng
pubDatetime: 2023-06-10T04:06:31Z
slug: sp-5917-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 5917题解
---

# 题意

给定一个数 $n$，求 $n!$ 的位数。

# 思路

我们知道整数 $n$ 的位数的计算方法为 $\log_{10}{n} $，故 $n!$ 的位数为 $\log_{10}{n!}$。如果要求出 $n!$ 的具体值，计算会很慢。但是如果仅仅是求阶乘的位数，可以用斯特林公式解决。

斯特林公式：$n!\approx \sqrt{2\times \pi \times n} \times\left ( \frac{n}{e} \right )$

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
#define pi 3.141592653589793238462643
#define e 2.71828182845904523536
long long l(long long n){
    long long s=1;
    if (n>3){
    	s=log10(2*pi*n)/2+log10(n/e)*n+1;
	}    
    return s;
}
int main(){
	long long t;
	cin>>t;
	while (t--){
		long long n;
		cin>>n;
		cout<<l(n)<<endl;
	}
	return 0;
}

```
