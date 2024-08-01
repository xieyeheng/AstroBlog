---
title: SP 27450题解
author: xieyeheng
pubDatetime: 2023-07-04T04:06:31Z
slug: sp-27450-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 27450题解
---
# 思路

这道题让我们计算括号匹配方案数，我们可以使用 DP 来做这道题。

在这个题中，我们用 $dp[i][j]$ 表示前 $i$ 个括号中，以第 $i$ 个括号为结尾的合法方案数。其中 $j=0$ 表示以左括号为结尾，$j=1$ 表示以右括号为结尾。因为题目说可以有空串，所以将 $dp[0][1]$ 设置为 $1$，表示空字符串也是一个合法的方案。

接下来，两层循环，一层遍历字符串的每一个字符，另一层遍历 $dp$ 数组的每一列。遍历时判断该字符是左括号还是右括号，然后更新一下状态。

最后，输出 $dp[0][1]$ 的值，即为所求的括号匹配的方案数。



------------


大体思路不是很难，但是要注意一些细节：

+ 取模。题目要求答案对 $1000000007$ 取模。

+ 空串。题目允许空串，要记得处理。

+ 多测。由于是多组数据测试，所以要记得清空 $dp$ 数组。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
const int  N=1e3+10;
const int MOD=1e9+7;
char s[N];
int dp[N][2];
int t;
int main(){
    cin>>t;
    while (t--){
        memset(dp,0,sizeof(dp));
        int ans=1;
        cin>>s;
        int n=strlen(s);
        dp[0][1]=1;
        for (int i=0;i<n;i++){
            if (s[i]=='(')
                for (int j=N-1;j>=1;j--){
                    dp[j][0]=(dp[j-1][0]+dp[j-1][1])%MOD;
                }
            else {
                for (int j=0;j<N-1;j++){
                    dp[j][1]=(dp[j+1][0]+dp[j+1][1])%MOD;
                }
                dp[0][1]=(dp[0][1]+1)%MOD;
            }
        }
        cout<<dp[0][1]<<endl;
    }
    return 0;
}
```
