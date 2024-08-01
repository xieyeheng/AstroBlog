---
title: SP 1419题解
author: xieyeheng
pubDatetime: 2023-07-11T04:06:31Z
slug: sp-1419-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 1419题解
---

# 思路

首先看这个数据范围是 $n \le 2\times10^{9}$，我们是不可能使用暴力解决这个问题的，所以我们可以考虑找规律解决。

我们首先规定一堆 $n$ 个物品,两个人轮流从这堆物品中取物。每次至少取一个，最多取 $m$ 个，取到最后一个者胜。（本题中 $m=9$）

显然，如果 $n=m+1$，那么由于一次最多只能取 $m$ 个,所以,无论先取者拿走多少个，后取者都能够一次拿走剩余的物品，**后手必胜**，反之，先手必胜。

然后我们可以总结出规律：若 $(m+1)\mid n$，则先手必败，否则先手必胜。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
int n;
int main(){
	cin>>n;
	if (n%10!=0){
		cout<<"1"<<endl<<n%10<<endl;
	}
	else {
		cout<<"2"<<endl;
	}
	return 0;
}
```

# 后话

~~细读一遍题目后发现是[巴什博奕](https://baike.baidu.com/item/%E5%B7%B4%E4%BB%80%E5%8D%9A%E5%BC%88)。~~