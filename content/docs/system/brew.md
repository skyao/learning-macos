---
title: "Brew"
linkTitle: "Brew"
weight: 211
date: 2021-04-26
description: >
  Brew安装和设置
---



### 介绍

https://brew.sh/

### 安装

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

偶然会因为网络问题可以先设置代码再执行上面这段安装代码。代理设置方式如底下描述，对安装脚本也是适用的。

查看安装之后的版本：

```bash
% brew --version
Homebrew 3.1.5
Homebrew/homebrew-core (git revision 5e014bf244; last commit 2021-05-02)
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

也可以使用 socks5 代理，地址需要指定为 socks5 格式：

```bash
$ export ALL_PROXY=socks5://127.0.0.1:11080

$ brew install wget
Updating Homebrew...
==> Installing dependencies for wget: gettext, libunistring and libidn2
==> Installing wget dependency: gettext
==> Downloading https://homebrew.bintray.com/bottles/gettext-0.20.1.catalina.bot
==> Downloading from https://akamai.bintray.com/10/107d7f386fbeea6979f9376cdbbcf
######################################################################## 100.0%
==> Pouring gettext-0.20.1.catalina.bottle.tar.gz
```

#### 代理快捷设置

修改 `~/.zshrc` 文件，加入以下内容：

```bash
alias proxyon='export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890'
alias proxyoff='unset https_proxy http_proxy all_proxy'
```

这样就可以方便的在需要时设置brew的代理了。