---
title: 八校联考--T3
author: xieyeheng
pubDatetime: 2023-05-02T04:06:31Z
slug: ba-xiao-lian-kao-t3
featured: false
draft: false
tags:
  - 考试复盘
description:
  八校联考--T3
---

# 题面

图书馆中每本书都有一个图书编码，可以用于快速检索图书，这个图书编码是一个正整数。 每位借书的读者手中有一个需求码，这个需求码也是一个正整数。如果一本书的图书编码恰好以读者的需求码结尾，那么这本书就是这位读者所需要的。 小 D 刚刚当上图书馆的管理员，她知道图书馆里所有书的图书编码，她请你帮她写一个程序，对于每一位读者，求出他所需要的书中图书编码最小的那本书，如果没有他需要的书，请输出$-1$。


# 思路

输入完图书编码后排序一边，然后遍历所有编码，判断读者是否需要该书。需要则输出编码，最后没书了就输出 -1

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
int s[1010];
int n,q,w,num;
bool check(int a,int b){
    int i=1;
    while(i<=a&&i<=b){
        if(a%i!=b%i)return false;
        i*=10;
    }
    return true;
}
int main(){
	//freopen("library.in","r",stdin);
	//freopen("library.out","w",stdout);
    cin>>n>>q;
    for (int i=1;i<=n;i++)cin>>s[i];
    sort(s+1,s+n+1);
    for (int i=1;i<=q;i++){
        cin>>w>>num;
        bool flag=true;
        for (int j=1;j<=n;j++){
            if (s[j]>=num and check(s[j],num)){
                cout<<s[j]<<endl;
                flag=false;
                break;
            }
        }
        if (flag)cout<<-1<<endl;
    }
    //fclose(stdin);
    //fclose(stdout);
    return 0;
}
```
[![Page Views Count](https://badges.toozhao.com/badges/01GZE0GHZ2V4M4KX4C41TABFXM/orange.svg)](https://badges.toozhao.com/stats/01GZE0GHZ2V4M4KX4C41TABFXM "Get your own page views count badge on badges.toozhao.com")