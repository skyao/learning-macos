---
title: "sdkman"
linkTitle: "sdkman"
weight: 20
date: 2022-03-20
description: >
  管理 SDK 的多个版本
---

## 介绍

SDKMAN 是一款管理多版本 SDK 的工具，可以实现在多个版本间的快速切换。

https://sdkman.io/

## 安装

安装方法参考官方文档：

https://sdkman.io/install

```bash
$ curl -s "https://get.sdkman.io" | bash
```

安装完成后，关闭当前终端重新打开新的终端，或者在当前终端中执行下面的命令立即更新：

```bash
source "/Users/sky/.sdkman/bin/sdkman-init.sh"
```

验证一下安装的版本：

```bash
$ sdk version  

SDKMAN 5.14.1
```

默认情况下，sdkman 安装在 HOME 下的 `.sdkman` 子目录中：

```bash
$ ls ~/.sdkman 
archives   bin        candidates contrib    etc        ext        src        tmp        var
```

### m1 下开启 rosetta2 兼容模式

在 m1 下，默认 rosetta2 兼容模式是关闭的，因此在 m1 上只能列出来 arm64 版本的 SDK。

以 java SDK 为例:

```bash
$ sdk list java

================================================================================
Available Java Versions for macOS ARM 64bit
================================================================================
 Vendor        | Use | Version      | Dist    | Status     | Identifier
--------------------------------------------------------------------------------
 Corretto      |     | 17.0.2.8.1   | amzn    |            | 17.0.2.8.1-amzn     
 Java.net      |     | 19.ea.13     | open    |            | 19.ea.13-open       
               |     | 19.ea.12     | open    |            | 19.ea.12-open       
               |     | 19.ea.11     | open    |            | 19.ea.11-open       
               |     | 19.ea.10     | open    |            | 19.ea.10-open       
               |     | 19.ea.4.lm   | open    |            | 19.ea.4.lm-open     
               |     | 18           | open    |            | 18-open             
               |     | 18.ea.35     | open    |            | 18.ea.35-open       
               |     | 17.0.2       | open    |            | 17.0.2-open         
               | >>> | 11.0.2       | open    | local only | 11.0.2-open         
 Liberica      |     | 17.0.2.fx    | librca  |            | 17.0.2.fx-librca    
               |     | 17.0.2       | librca  |            | 17.0.2-librca       
               |     | 11.0.14      | librca  |            | 11.0.14-librca      
               |     | 8.0.322      | librca  |            | 8.0.322-librca      
 Microsoft     |     | 17.0.2       | ms      |            | 17.0.2-ms           
               |     | 11.0.14      | ms      |            | 11.0.14-ms          
 Oracle        |     | 17.0.2       | oracle  |            | 17.0.2-oracle       
 SapMachine    |     | 17.0.2       | sapmchn |            | 17.0.2-sapmchn      
 Temurin       |     | 17.0.2       | tem     |            | 17.0.2-tem          
 Zulu          |     | 17.0.2       | zulu    |            | 17.0.2-zulu         
               |     | 17.0.2.fx    | zulu    |            | 17.0.2.fx-zulu      
               |     | 11.0.14      | zulu    |            | 11.0.14-zulu        
               |     | 8.0.322      | zulu    |            | 8.0.322-zulu     
```

以上是支持 macos + arm64 的 JDK。

如果要开启 rosetta2 兼容模式，需要修改 sdkman 的配置，`vi ~/.sdkman/etc/config`:

```properties
sdkman_auto_answer=false
sdkman_auto_complete=true
sdkman_auto_env=false
sdkman_auto_update=true
sdkman_beta_channel=false
sdkman_checksum_enable=true
sdkman_colour_enable=true
sdkman_curl_connect_timeout=7
sdkman_curl_max_time=10
sdkman_debug_mode=false
sdkman_insecure_ssl=false
sdkman_rosetta2_compatible=false	# 修改这里为 true
sdkman_selfupdate_feature=true
```

将 sdkman_rosetta2_compatible 修改为 true。修改后在当前终端中执行下面的命令立即更新：

```bash
source "/Users/sky/.sdkman/bin/sdkman-init.sh"
```

此时再执行 list java 就能看到更多的安装选项了：

```bash
$ sdk list java

================================================================================
Available Java Versions for macOS 64bit
================================================================================
 Vendor        | Use | Version      | Dist    | Status     | Identifier
--------------------------------------------------------------------------------
 Corretto      |     | 17.0.2.8.1   | amzn    |            | 17.0.2.8.1-amzn     
               |     | 11.0.14.10.1 | amzn    |            | 11.0.14.10.1-amzn   
               |     | 11.0.14.9.1  | amzn    |            | 11.0.14.9.1-amzn    
               |     | 8.322.06.2   | amzn    |            | 8.322.06.2-amzn     
               |     | 8.322.06.1   | amzn    |            | 8.322.06.1-amzn     
 Gluon         |     | 22.0.0.3.r17 | gln     |            | 22.0.0.3.r17-gln    
               |     | 22.0.0.3.r11 | gln     |            | 22.0.0.3.r11-gln    
 GraalVM       |     | 22.0.0.2.r17 | grl     |            | 22.0.0.2.r17-grl    
               |     | 22.0.0.2.r11 | grl     |            | 22.0.0.2.r11-grl    
               |     | 21.3.1.r17   | grl     |            | 21.3.1.r17-grl      
               |     | 21.3.1.r11   | grl     |            | 21.3.1.r11-grl      
               |     | 21.2.0.r16   | grl     |            | 21.2.0.r16-grl      
               |     | 21.2.0.r11   | grl     |            | 21.2.0.r11-grl      
               |     | 20.3.5.r11   | grl     |            | 20.3.5.r11-grl      
               |     | 19.3.6.r11   | grl     |            | 19.3.6.r11-grl      
 Java.net      |     | 19.ea.13     | open    |            | 19.ea.13-open       
               |     | 19.ea.12     | open    |            | 19.ea.12-open       
               |     | 19.ea.11     | open    |            | 19.ea.11-open       
               |     | 19.ea.10     | open    |            | 19.ea.10-open       
               |     | 19.ea.4.lm   | open    |            | 19.ea.4.lm-open     
               |     | 19.ea.1.pma  | open    |            | 19.ea.1.pma-open    
               |     | 18           | open    |            | 18-open             
               |     | 18.ea.35     | open    |            | 18.ea.35-open       
               |     | 17.0.2       | open    |            | 17.0.2-open         
               | >>> | 11.0.2       | open    |            | 11.0.2-open         
 Liberica      |     | 17.0.2.fx    | librca  |            | 17.0.2.fx-librca    
               |     | 17.0.2       | librca  |            | 17.0.2-librca       
               |     | 11.0.14.fx   | librca  |            | 11.0.14.fx-librca   
               |     | 11.0.14      | librca  |            | 11.0.14-librca      
               |     | 8.0.322.fx   | librca  |            | 8.0.322.fx-librca   
               |     | 8.0.322      | librca  |            | 8.0.322-librca      
 Liberica NIK  |     | 22.0.0.2.r17 | nik     |            | 22.0.0.2.r17-nik    
               |     | 22.0.0.2.r11 | nik     |            | 22.0.0.2.r11-nik    
               |     | 21.3.1.r17   | nik     |            | 21.3.1.r17-nik      
               |     | 21.3.1.r11   | nik     |            | 21.3.1.r11-nik      
               |     | 21.3.0.r17   | nik     |            | 21.3.0.r17-nik      
               |     | 21.3.0.r11   | nik     |            | 21.3.0.r11-nik      
               |     | 21.2         | nik     |            | 21.2-nik            
 Microsoft     |     | 17.0.2       | ms      |            | 17.0.2-ms           
               |     | 11.0.14      | ms      |            | 11.0.14-ms          
 Oracle        |     | 17.0.2       | oracle  |            | 17.0.2-oracle       
 SapMachine    |     | 17.0.2       | sapmchn |            | 17.0.2-sapmchn      
               |     | 11.0.14      | sapmchn |            | 11.0.14-sapmchn     
               |     | 11.0.14.1    | sapmchn |            | 11.0.14.1-sapmchn   
 Semeru        |     | 17.0.2       | sem     |            | 17.0.2-sem          
               |     | 11.0.14      | sem     |            | 11.0.14-sem         
               |     | 11.0.14.1    | sem     |            | 11.0.14.1-sem       
               |     | 8.0.322      | sem     |            | 8.0.322-sem         
 Temurin       |     | 17.0.2       | tem     |            | 17.0.2-tem          
               |     | 11.0.14      | tem     |            | 11.0.14-tem         
               |     | 8.0.322      | tem     |            | 8.0.322-tem         
 Trava         |     | 11.0.9       | trava   |            | 11.0.9-trava        
               |     | 8.0.232      | trava   |            | 8.0.232-trava       
 Zulu          |     | 17.0.2       | zulu    |            | 17.0.2-zulu         
               |     | 17.0.2.fx    | zulu    |            | 17.0.2.fx-zulu      
               |     | 11.0.14      | zulu    |            | 11.0.14-zulu        
               |     | 11.0.14.fx   | zulu    |            | 11.0.14.fx-zulu     
               |     | 8.0.322      | zulu    |            | 8.0.322-zulu        
               |     | 8.0.322.fx   | zulu    |            | 8.0.322.fx-zulu     
               |     | 7.0.332      | zulu    |            | 7.0.332-zulu 
```

## 使用

> 备注：M1 下可用。

使用方法参考官方文档：

https://sdkman.io/usage

具体的使用可以看后面章节。

## 参考文档

- [Usage - SDKMAN! the Software Development Kit Manager](https://sdkman.io/usage)
- [使用 sdkman 在 M1 Mac 上 安装 graalvm jdk (atbug.com)](https://atbug.com/install-graalvm-on-m1-mac-with-sdkman/)：鸣谢晓晖同学！