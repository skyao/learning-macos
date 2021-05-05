---
title: "NTFS支持"
linkTitle: "NTFS支持"
weight: 132
date: 2021-04-26
description: >
  NTFS格式的支持
---



### 简单方式：开启原生支持

考虑到日常对ntfs分区的写入非常少，另外盘符也通常比较固定，因此，简单开启 macos的ntfs写入功能就可以了。

具体方式为修改 /etc/fstab 文件（如果文件不存在则新建该文件），加入以下内容：

```
LABEL=**NAME** none ntfs rw,auto,nobrowsez          
```

name 可以通过 `diskutil list` 来查看，以下是示例：

```bash
LABEL=download none ntfs rw,auto,nobrowse
LABEL=movie none ntfs rw,auto,nobrowse
LABEL=win10 none ntfs rw,auto,nobrowse
```

重启即可。Catalina/big sur下非常方便，自动mount完成而且方便访问。

- [打开Mac OSX原生的读写NTFS功能](https://www.jianshu.com/p/e6116dd06a43)

### 复杂方式：使用第三方软件

下面这个文章介绍的非常清晰：

https://applehint.com/t/how-to-write-to-ntfs-drives-in-macos-catalina-and-mojave/1262

- [Mac读写NTFS Paragon NTFS for Mac 15.5.53兼容10.15macOS Catalina无限试用](https://www.douban.com/note/722969555/)

### 其他

反思：对于移动硬盘/做数据备份和存储的盘符，用 exfat 格式应该是麻烦最少的，各个操作系统都可以支持。



