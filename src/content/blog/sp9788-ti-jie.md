---
title: SP 9788题解
author: xieyeheng
pubDatetime: 2023-06-10T04:06:31Z
slug: sp-9788-ti-jie
featured: false
draft: false
tags:
  - 题解
description:
  SP 9788题解
---

# 思路

因为 `set` 有去重特性，我们用 `set` 来储存所有的朋友，求出朋友总数后减去 Bob 的直接朋友就是他的朋友的朋友。

# 代码

```cpp
#include<bits/stdc++.h>
using namespace std;
int main() {
    int n,f,m;
    cin>>n;
    set<int> st;
    for (int i=1;i<=n;i++) {
        cin>>f>>m;
        st.insert(f);
        for (int i=1;i<=m;i++) {
            cin>>f;
            st.insert(f);
        }
    }
    cout<<st.size()-n<<endl;
    return 0; 
}
```
