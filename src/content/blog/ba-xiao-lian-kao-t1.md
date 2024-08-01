---
title: 八校联考--T1
author: xieyeheng
pubDatetime: 2023-05-02T04:06:31Z
slug: ba-xiao-lian-kao-t1
featured: false
draft: false
tags:
  - 考试复盘
description:
  八校联考--T1
---

# 总览

题面点此下载 [link](https://pan.huang1111.cn/s/kwWziB/)

# 题面

扫雷游戏是一款十分经典的单机小游戏。在 $n$ 行 $m$ 列的雷区中有一些格子含有地雷（称之为地雷格），其他格子不含地雷（称之为非地雷格）。玩家翻开一个非地雷格时，该格将会出现一个数字——提示周围格子中有多少个是地雷格。游戏的目标是在不翻出任何地雷格的条件下，找出所有的非地雷格。

现在给出 $n$ 行 $m$ 列的雷区中的地雷分布，要求计算出每个非地雷格周围的地雷格数。

注：一个格子的周围格子包括其上、下、左、右、左上、右上、左下、右下八个方向上与之直接相邻的格子。

# 思路

用二维数组存图，直接暴力循环枚举，注意访问数组时不要越界。

```cpp
//80分
#include<bits/stdc++.h>
using namespace std;
const int MAXN=105;
int n,m;
char mp[MAXN][MAXN];
int search(int x,int y){
	int ret=0;
	if (mp[x][y]=='*'){
		return -1;
	}
	if (x!=m){
		if (mp[x+1][y]=='*'){
			ret++;
		}
	}
	if (x!=1){
		if (mp[x-1][y]=='*'){
			ret++;
		}
	}
	if (y!=n){
		if (mp[x][y+1]=='*'){
			ret++;
		}
	}
	if (y!=1){
		if (mp[x][y-1]=='*'){
			ret++;
		}
	}
	if (y!=1 and x!=1){
		if (mp[x-1][y+1]=='*'){
			ret++;
		}
		if (mp[x-1][y-1]=='*'){
			ret++;
		}
		if (mp[x+1][y+1]=='*'){
			ret++;
		}
		if (mp[x+1][y-1]=='*'){
			ret++;
		}
	}
	else {
		if (x==1){
			if (mp[x+1][y+1]=='*'){
				ret++;
			}
			if (mp[x+1][y-1]=='*'){
				ret++;
			}
		}
		if (y==1){
			if (mp[x-1][y+1]=='*'){
				ret++;
			}
			if (mp[x+1][y+1]=='*'){
				ret++;
			}
		}
	}
	return ret;
}
int main(){
	//freopen("treasure.in","r",stdin);
	//freopen("treasure.out","w",stdout);
	cin>>n>>m;
	for (int i=1;i<=n;i++){
		for (int j=1;j<=m;j++){
			cin>>mp[i][j];
		}
	}
	for (int i=1;i<=n;i++){
		for (int j=1;j<=m;j++){
			int tmp=search(i,j);
			if (tmp!=-1){
				cout<<tmp; 
			}
			else {
				cout<<"*";
			}
		}
		cout<<endl;
	}
	//fclose(stdin);
	//fclose(stdout); 
	return 0;
}
```
[![Page Views Count](https://badges.toozhao.com/badges/01GZE0349HD18PQ1PV77F709FA/blue.svg)](https://badges.toozhao.com/stats/01GZE0349HD18PQ1PV77F709FA "Get your own page views count badge on badges.toozhao.com")

