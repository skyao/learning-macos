---
title: "JDK Mission Control"
linkTitle: "Mission Control"
weight: 120
date: 2022-03-21
description: >
  JDK Mission Control
---



## 介绍

https://www.oracle.com/java/technologies/jdk-mission-control.html

在 zule jdk上，使用的是 zulu mission control：

https://www.azul.com/products/components/zulu-mission-control/

支持

## 安装

### 使用 sdkman 安装

默认的 jmc 8.1.1.51-zulu 版本不支持 m1：

```bash
$ sdk install jmc   

Stop! jmc 8.1.1.51-zulu is not available. Possible causes:
 * 8.1.1.51-zulu is an invalid version
 * jmc binaries are incompatible with your platform
 * jmc has not been released yet

Tip: see all available versions for your platform:

  $ sdk list jmc
```

用 `sdk list jmc ` 命令查看发现有 8.1.1.57-zulu 版本：

```bash
$ sdk list jmc                 

================================================================================
Available Jmc Versions
================================================================================
 >   8.1.1.57-zulu 
```

用这个 8.1.1.57-zulu 版本继续安装：

```bash
$ sdk install jmc 8.1.1.57-zulu

Downloading: jmc 8.1.1.57-zulu

In progress...

######################################################################### 100.0%

Repackaging JMC zulu 8.1.1.57-zulu...

Done repackaging...

Installing: jmc 8.1.1.57-zulu
mv: /Users/sky/.sdkman/candidates/jmc/8.1.1.57-zulu is not a directory
Done installing!


Setting jmc 8.1.1.57-zulu as default.
```

安装时似乎出错了，`ls ~/.sdkman/candidates/jmc` 检查 .sdkman 目录下发现安装的确出错了：

```bash
$ ls -l ~/.sdkman/candidates/jmc
lrwxr-xr-x  1 sky  staff   13  3 21 08:18 current -> 8.1.1.57-zulu
```

再安装一次：

```bash
$ sdk install jmc 8.1.1.57-zulu

Found a previously downloaded jmc 8.1.1.57-zulu archive. Not downloading it again...


Installing: jmc 8.1.1.57-zulu
Done installing!

Do you want jmc 8.1.1.57-zulu to be set as default? (Y/n): Y

Setting jmc 8.1.1.57-zulu as default.
```

这次对了：

```bash
$ ls -l ~/.sdkman/candidates/jmc
drwxr-xr-x  6 sky  staff  192  3 21 07:47 8.1.1.57-zulu
lrwxr-xr-x  1 sky  staff   13  3 21 08:18 current -> 8.1.1.57-zulu
```

但执行时报错：

```bash
$ jmc version
The operation couldn’t be completed. Unable to locate a Java Runtime that supports jmc.
Please visit http://www.java.com for information on installing Java.

$ which jmc
/usr/bin/jmc
```

Jmc 指向的是 `/usr/bin/jmc`，这个应该是我之前手工安装 zule jdk 时复制过去的文件。

```bash
sudo rm -rf /usr/bin/jmc
rm: /usr/bin/jmc: Operation not permitted
```





### 手工安装

https://www.azul.com/products/components/zulu-mission-control/#block-download



## 配置

TBD







