---
title: 记一次解决核显频率锁在 300MHz 的经历
author: xieyeheng
pubDatetime: 2024-06-10T04:06:31Z
slug: gpu300mhz
featured: false
draft: false
tags:
  - 闲话
description:
  记一次解决核显频率锁在 300MHz 的经历
---

## 起因

我在打《鸣潮》时顿觉卡顿，遂打开 MSI Afterburner 进行查看，发现核显频率只有 300MHz。

## 解决方法

1. 下载 [DDU](https://www.wagnardsoft.com/display-driver-uninstaller-DDU)，进入安全模式卸载显卡驱动。
2. 重启到正常系统，在 Intel 的官网下载驱动或者 `英特尔® 驱动程序和支持助理`，安装驱动。
3. 解决

## 总结

其实方法不难，不过我摸索了好久，主要是网上搜到的方法都没有，包括放静电，加散热等。