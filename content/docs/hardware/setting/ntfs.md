---
title: "NTFS支持"
linkTitle: "NTFS支持"
weight: 132
date: 2021-04-26
description: >
  NTFS格式的支持
---



### ~~简单方式：开启原生支持~~

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


{{% alert title="警告" color="warning" %}}
最新版本的Big Sur(11.4+)之后这个功能不再有效
{{% /alert %}}


### 复杂方式：使用第三方软件

对比之后选择采用 Tuxera Disk Manager 来支持 ntfs 格式。

![tuxera](./images/tuxera.png)

### 其他

反思：对于移动硬盘/做数据备份和存储的盘符，用 exfat 格式应该是麻烦最少的，各个操作系统都可以支持。



