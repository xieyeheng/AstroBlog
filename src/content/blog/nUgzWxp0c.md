---
title: SP 9686题解
author: xieyeheng
pubDatetime: 2023-11-04T04:06:31Z
slug: sp-9686
featured: false
draft: false
tags:
  - 题解
description:
  SP 9686题解
---

# 思路

数据范围是 $1\leq N\leq16$，果断考虑手算 + 找规律。徒手画出前几个图形，拿去 OEIS 找规律，发现正好可以和[这个](https://oeis.org/A006534)吻合，于是就可以水过了。

至于找规律的过程，如下：

+ 1 个三角形：1 种

+ 2 个三角形：2 种

+ 3 个三角形：3 种（这 3 种都没什么好说的，不占用太多篇幅）

+ 4 个三角形：4 种，如图所示（这个题面有给）：

![](https://www.spoj.com/content/john_jones:yummy.jpg)

+ 5 个三角形：

![](https://pic.florr.cloud/file/151e3d993927db7e4a261.png)


# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
long long n,a[30]={0,1,1,1,4,6,19,43,120,307,866,2336,6588,18373,52119,147700,422016,1207477,3471067,
		9999135,28893560,83665729,242826187,706074369,2056870697,6001555275,17538335077,51323792789};
int main(){
	cin>>n;
	for (int i=1;i<=n;i++){
		int tmp;
		cin>>tmp;
		cout<<"Case #"<<i<<": "<<a[tmp]<<endl;
	}
	return 0;
}
```
