---
title: "showmount 命令"
linkTitle: "showmount 命令"
weight: 10
date: 2021-04-26
description: >
  showmount 命令可以用来查看目标服务器上可以mount的nfs资源
---



```bash
$ showmount -e 192.168.0.1 

Exports list on 192.168.0.1:
/mnt/download                       192.168.0.0/16
/mnt/shared                         192.168.0.0/16
```

