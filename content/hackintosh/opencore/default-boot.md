---
title: "Open Core设置默认启动项"
linkTitle: "默认启动项"
weight: 3101
date: 2021-05-02
description: >
  Open Core默认启动项
---



### big sur下简单设置

Big Sur版本下简单的多，可以直接打开 "系统偏好设置" -> "启动磁盘" ，选择需要启动的系统即可。

### 其他系统

需要使用 OpenCoreConfiguator 工具，设置 MISC -> Security -> AllowSetDefault 的值为 true。

然后重启，在OC引导选择洁面上，选择好某一项，按 `crtl+enter`，以后这一项就会是默认启动项。

具体操作参考文章：

- [OpenCore引导开机倒计时自动进入指定系统盘，修改默认启动项教程 - 黑苹果屋 (imacos.top)](http://imacos.top/2020/09/16/1027-2/)

