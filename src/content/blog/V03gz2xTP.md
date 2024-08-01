---
title: SP 2157题解
author: xieyeheng
pubDatetime: 2023-11-04T04:06:31Z
slug: sp-2157-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 2157题解
---

# 思路

用三个 `string` 存下三个数，然后判断哪个数里有字母（即有墨水印记），然后拿另外两个没被污染的数算出被污染的数。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
int t,ans1,ans2,ans3;
string n;
int check(string s){
  	// 将 string 转成 int
  	// 若该 string 里有不是数字的字符，返回 -1
	int ret=0;
	for (int i=0;i<s.length();i++){
		if (s[i]<'0' or s[i]>'9') return -1;
		else {
			ret*=10;
			ret+=s[i]-'0';
		}
	}
	return ret;
}
int main(){
//	cin>>n;
//	cout<<check(n)<<endl;
	cin>>t;
	while (t--){
		string s1,s2,s3;
		string add,equal;
		cin>>s1>>add>>s2>>equal>>s3;
		int a=check(s1);
		int b=check(s2);
		int c=check(s3);
		if (a==-1) a=c-b;
		if (b==-1) b=c-a;
		if (c==-1) c=a+b;
		cout<<a<<" + "<<b<<" = "<<c<<endl;
	}
	return 0;
}
```
