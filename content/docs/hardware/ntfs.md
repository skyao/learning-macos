---
title: "NTFS支持"
linkTitle: "NTFS支持"
weight: 110
date: 2021-04-26
description: >
  NTFS格式的支持
---


下面这个文章介绍的非常清晰：

https://applehint.com/t/how-to-write-to-ntfs-drives-in-macos-catalina-and-mojave/1262

- [打开Mac OSX原生的读写NTFS功能](https://www.jianshu.com/p/e6116dd06a43)
- [Mac读写NTFS Paragon NTFS for Mac 15.5.53兼容10.15macOS Catalina无限试用](https://www.douban.com/note/722969555/)

发现破解版本比较啰嗦，而日常对ntfs分区的写入应该非常少，另外盘符也通常比较固定，因此，简单开发macos的ntfs写入功能就可以了。具体为修改 /etc/fstab 文件，加入一下几行：

```bash
LABEL=download none ntfs rw,auto,nobrowse
LABEL=movie none ntfs rw,auto,nobrowse
LABEL=win10 none ntfs rw,auto,nobrowse
```

重启即可。Catalina下非常方便，自动mount完成而且方便访问，和平时没差别。

反思：对于移动硬盘/做数据备份和存储的盘符，用 exfat 格式应该是麻烦最少的，各个操作系统都可以支持。



