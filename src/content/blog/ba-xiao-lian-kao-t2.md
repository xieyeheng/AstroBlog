---
title: 八校联考--T2
author: xieyeheng
pubDatetime: 2023-05-02T04:06:31Z
slug: ba-xiao-lian-kao-t2
featured: false
draft: false
tags:
  - 考试复盘
description:
  八校联考--T2
---

# 题面

~~暂时找不到题面~~ fixed

![](https://xieyeheng.github.io/post-images/1683026052350.jpeg)

# 思路

这是一个找规律的题，赛时写了暴力，赛后顿悟。

# 代码

代码如下

```cpp
#include<bits/stdc++.h>
using namespace std;
int n,y,x;
int k;
int c(){
	if(x==1) return y;
	if(y==1) return 4*n-2-x;
	if(y==n) return n-1+x;
	if(x==n) return 3*n-1-y;
}
int main(){
	//freopen("game.in","r",stdin);
	//freopen("game.out","w",stdout);
	cin>>n>>x>>y;
	while (x>1 and y>1 and x<n and y<n){
		k+=4*(n-1);
		n-=2;
		x--;
		y--;
	}
	cout<<k+c();
	//fclose(stdin);
	//fclose(stdout);
	return 0;
}
```
[![Page Views Count](https://badges.toozhao.com/badges/01GZE085CM07FBAHE8BVQRB2DZ/green.svg)](https://badges.toozhao.com/stats/01GZE085CM07FBAHE8BVQRB2DZ "Get your own page views count badge on badges.toozhao.com")
