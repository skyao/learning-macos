---
title: "解决i210在big sur下panic的问题"
linkTitle: "i210 panic"
weight: 3200
date: 2021-08-17
description: >
  解决i210在big sur下panic的问题
---



### 问题描述

华硕 x299 ws pro 主板自带两个intel i210 千兆有线网卡，在windows下使用正常，但是在安装big sur时会造成死机（系统panic）。在bios中屏蔽这两个网卡之后，可以正常安装 big sur 并进入系统。但是，如果再开启i210网卡，会在进入系统之后1-2分钟因内核panic而死机。

尝试用 intel 的几个主流驱动：

- intelmausi.kext：无效，而且明确说明不支持i210
- IntelMausiEthernet.kext：无效
- appleIGB.kext: 小众驱动，据说支持Intel 82575, 82576, 82580, dh89xxcc, i350, i210 and i211的网卡，但亲测无效。参考：[Inteli350,i210,i211小众网卡驱动，亲测微星z390战斧有效-远景论坛-微软极客社区 (pcbeta.com)](https://bbs.pcbeta.com/viewthread-1889369-1-1.html)

### 解决方案

参考：[Problems with Big Sur (macinabox) VM and Intel i210 network card after upgrading to 11.4 - VM Engine (KVM) - Unraid](https://forums.unraid.net/topic/109718-problems-with-big-sur-macinabox-vm-and-intel-i210-network-card-after-upgrading-to-114/)

下载附近中的i210.kext，加入oc引导文件，发现可以在网卡开启的情况下顺利进入big sur安装界面的图形界面，看样子应该是解决了。

稍后再确认。