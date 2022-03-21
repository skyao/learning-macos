---
title: "Maven"
linkTitle: "Maven"
weight: 20
date: 2022-03-08
description: >
  Maven的安装配置
---



## 安装

### 使用 sdkman 安装maven

```bash
$ sdk install maven

Downloading: maven 3.8.5

In progress...

######################################################################### 100.0%

Installing: maven 3.8.5
Done installing!

Setting maven 3.8.5 as default.
```

检查 maven 的安装， mvn 没有 arch 的差异，完全取决于当前 maven 使用的 java sdk。因此使用不同 java sdk 时的输出是不一样的。

```bash
$ sdk use java 11.0.14-zulu
$ mvn --version
Apache Maven 3.8.5 (3599d3414f046de2324203b78ddcf9b5e4388aa0)
Maven home: /Users/sky/.sdkman/candidates/maven/current
Java version: 11.0.14, vendor: Azul Systems, Inc., runtime: /Users/sky/.sdkman/candidates/java/11.0.14-zulu/zulu-11.jdk/Contents/Home
Default locale: zh_CN_#Hans, platform encoding: UTF-8
OS name: "mac os x", version: "12.3", arch: "aarch64", family: "mac"
```

## 配置

TBD







