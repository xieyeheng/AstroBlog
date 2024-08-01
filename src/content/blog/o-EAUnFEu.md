---
title: 如何解除极域网控
author: xieyeheng
pubDatetime: 2023-10-05T04:06:31Z
slug: fuck-jiyu
featured: false
draft: false
tags:
  - 题解
description:
  一些工具，好像没啥用啊
---

~~一键关闭网控 - [以管理员模式运行！](https://cn-sy1.s3.rainyun.cn/xieyeheng/以管理员模式运行.exe)~~

链接已失效

### 1.关闭极域保护进程

在任务管理器找到 MasterHelper.exe 进程。

### 2.关闭极域的网控服务（是驱动？）

以管理员身份打开 cmd，输入
```
NET stop TDNetFilter
```

出现 “TDNetFilter 服务已成功停止” 字样即为成功。