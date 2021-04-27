---
title: "lsof命令"
linkTitle: "lsof命令"
weight: 411
date: 2021-04-26
description: >
  Macos的 lsof 网络命令
---


查看当前那些程序在监听端口：

```bash
sudo lsof -nP -iTCP -sTCP:LISTEN
```



- [使用 lsof 代替 Mac OS X 中的 netstat 查看占用端口的程序](https://tonydeng.github.io/2016/07/07/use-lsof-to-replace-netstat/)