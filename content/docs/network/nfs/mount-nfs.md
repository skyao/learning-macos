---
title: "挂载 nfs 磁盘"
linkTitle: "挂载 nfs 磁盘"
weight: 20
date: 2021-04-26
description: >
  通过mount命令挂载 nfs 磁盘到本机
---

先通过 showmount 查看目标服务器上可以挂载的 nfs 资源列表：

```bash
$ showmount -e 192.168.0.1 

Exports list on 192.168.0.1:
/mnt/download                       192.168.0.0/16
/mnt/shared                         192.168.0.0/16
```

手工 mount 这两个到本地：

```bash
mount -t nfs 192.168.0.1:/mnt/download /Users/sky/nfs/skyaio-download
mount -t nfs 192.168.0.1:/mnt/shared /Users/sky/nfs/skyaio-shared
```



参考资料：

- [macOS X Mount NFS Share / Set an NFS Client](https://www.cnblogs.com/mouseleo/p/9971661.html)
