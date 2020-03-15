---
date: 2019-03-05T07:00:00+08:00
title: Brew
menu:
  main:
    parent: "system"
weight: 271
description : "Brew"
---



### 介绍

https://brew.sh/

### 安装

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

查看安装之后的版本：

```bash
$ brew --version
Homebrew 2.2.10
Homebrew/homebrew-core (git revision 56d51c; last commit 2020-03-15)
```

### 代理设置

可以通过  `export ALL_PROXY=proxyIP:port` 方式设置代理（指向http代理）：

```bash
$ export ALL_PROXY=127.0.0.1:1087
$ brew install socat
Updating Homebrew...
==> Installing dependencies for socat: openssl@1.1 and readline
==> Installing socat dependency: openssl@1.1
==> Downloading https://homebrew.bintray.com/bottles/openssl@1.1-1.1.1d.catalina
==> Downloading from https://akamai.bintray.com/d7/d7f992ebfd78f80828051f6dc6a1a
######################################################################## 100.0%
==> Pouring openssl@1.1-1.1.1d.catalina.bottle.tar.gz

```

