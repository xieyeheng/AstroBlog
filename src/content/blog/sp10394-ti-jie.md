---
title: SP 10394题解
author: xieyeheng
pubDatetime: 2023-05-20T04:06:31Z
slug: sp-10394-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 10394题解
---

# 题意

通读题面，我们可以发现输入中给出了三个数据 $x,y,i$，$x$ 为质量，$y$ 为价值，$i$ 为数量。特别地，当 $i$ 为 $-1$ 时，该苹果包不存在。我们发现这是一个完全背包问题。

# 思路

完全背包与 01 背包类似，与 01 背包的区别仅在于一个物品可以选取多次次，而 01 背包仅能选取一次。

理解了完全背包的概念后，可以发现这题是一个完全背包的板子题，但是多了一个朋友的数量 $n$ 来约束需要购买的苹果包的数量。我们只需要在完全背包的板子里加上一个选择，判断数量是否超越朋友的数量即可。

完全背包模板练习题：[P1048 采药](https://www.luogu.com.cn/problem/P1048)。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
const int MAXN=1000000000;
struct Node{
	int x,count;
} a[105];
int main(){
	int n,k,t;
	cin>>t;
	while (t--){
		cin>>n>>k;
		for (int i=1;i<=k;i++){
			cin>>a[i].x;
			a[i].count=1;
			if (a[i].x==-1){
				a[i].x==MAXN;
			}
		}
		for (int i=2;i<=k;i++){
			for (int j=1;j<=i;j++){
				if ((a[i-j].x+a[j].x)<a[i].x and (a[i-j].count+a[j].count)<=n){
					a[i].x = a[i-j].x + a[j].x;
                    a[i].count = a[i-j].count + a[j].count;
				}
			}
		}
		if (a[k].x==MAXN) {
            cout<<"-1"<<endl;
        }
        else {
            cout<<a[k].x<<endl;
        }
	}
	return 0;
}
```

[![Page Views Count](https://badges.toozhao.com/badges/01H0VGGYEXHRKSWX8GP3479JQX/green.svg)](https://badges.toozhao.com/stats/01H0VGGYEXHRKSWX8GP3479JQX "Get your own page views count badge on badges.toozhao.com")
