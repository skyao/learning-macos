---
date: 2018-10-04T20:00:00+08:00
title: 硬件
weight: 100
description : "苹果Macos安装之后的硬件设置"
---

苹果Macos（尤其是黑苹果）安装之后的硬件设置。



### NTFS格式支持

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

## 监控类软件

### iStat Menus

参考：https://xclient.info/s/istat-menus-for-mac.html 

### HWMonitor

- [硬件检测 HWMonitor for Mac 6.26.1800 完善传感器信息 赠送：专业解决黑苹果无法检测温度的姿势](https://www.itpwd.com/284.html#)

### TG Pro

- [如何使用TG Pro for Mac风扇控制来冷却Mac电脑](https://blog.51cto.com/14370425/2417873)

### 温度监控

- [驱动硬件传感器获取 CPU 温度详细信息](https://zuiyu1818.cn/posts/Hac_CPU_sensors.html)

备注：以上三个，在我的黑苹果上，尝试无效，折腾时还把系统搞的差点启动不起来。放弃温度监控和风扇调速，让主板bios搞定吧。