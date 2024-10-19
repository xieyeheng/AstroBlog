---
title: 花都 GF 机房生存指南
author: xieyeheng
pubDatetime: 2023-04-20T04:06:31Z
slug: survive-in-hua-du-gf
featured: false
draft: false
tags:
  - 闲话
description:
  活下去，一起！
---

## E 听说系统退出

> 注意不是翼课网的系统，翼课网的退不了。

直接 `Windows+Tab` 然后新建桌面

## 极域网络控制解除

> 需要管理员权限

1. 打开任务管理器
2. 打开详细信息面板
3. 找到 MasterHelper.exe 并结束进程
4.  以管理员权限打开终端，结束网络控制服务

```
net stop TDNetFilter
```

## 极域软件控制解除

> 其实老师一般不会开这个（指周老师），就算开了也不会禁用 WPS 和 Dev-C++，而 WPS 是可以作为浏览器使用的。但如果开了这个，一般会顺便把“任务管理器”和“运行”都禁用了，因此需要一种绕过它的方法。

1. 打开 Dev-C++，新建原代码
2. 通过 `windows.h` 打开终端，具体代码如下（缺省源懒得删了）：

```cpp
#include<bits/stdc++.h>
#include<windows.h> 
using namespace std;
const int MAXN=1e5+10;
int n,m,arr[MAXN];
int main(){
	system("start cmd");
	return 0;
}

```


3. 通过 `tasklist` 列出正在运行的进程列表，找到 `MasterHelp.exe` 对应的 pid
4. 通过 `taskkill -pid 刚刚的pid` 结束进程。
5. 结束网络控制服务

```
net stop TDFileFilter
```


