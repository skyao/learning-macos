---
date: 2019-03-05T07:00:00+08:00
title: lsof命令
menu:
  main:
    parent: "network-command"
weight: 421
---



查看当前那些程序在监听端口：

```bash
sudo lsof -nP -iTCP -sTCP:LISTEN
```



- [使用 lsof 代替 Mac OS X 中的 netstat 查看占用端口的程序](https://tonydeng.github.io/2016/07/07/use-lsof-to-replace-netstat/)