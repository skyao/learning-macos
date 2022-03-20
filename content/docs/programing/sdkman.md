---
title: "sdkman"
linkTitle: "sdkman"
weight: 10
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

### 安装 JAVA SDK （for M1）

暂时使用 jdk 11，在 m1 上需要安装多个版本：

- openjdk 11: x64 版本
- zuul jdk : arm64 版本，作为原生版本使用

#### openjdk 11 （x86_64）

```bash
$ sdk install java 11.0.2-open   

Downloading: java 11.0.2-open

In progress...

################################################################################################################################ 100.0%

Repackaging Java 11.0.2-open...

Done repackaging...
Cleaning up residual files...

Installing: java 11.0.2-open
Done installing!


Setting java 11.0.2-open as default.
```

安装完成之后，可以通过 `sdk current` 命令看到当前正在使用的 sdk 和版本：

```bash
$ sdk current  

Using:

java: 11.0.2-open
```

检查一下当前的 java 设置：

```bash
$ which java
/Users/sky/.sdkman/candidates/java/current/bin/java

$ java --version
openjdk 11.0.2 2019-01-15
OpenJDK Runtime Environment 18.9 (build 11.0.2+9)
OpenJDK 64-Bit Server VM 18.9 (build 11.0.2+9, mixed mode)

$ env | grep JAVA_HOME
JAVA_HOME=/Users/sky/.sdkman/candidates/java/current
```

查看 一下本地文件的目录结构就清楚了：

```bash
$ ls -l /Users/sky/.sdkman/candidates/java/
total 0
drwxr-xr-x   9 sky  staff  288  1 18  2019 11.0.2-open
lrwxr-xr-x   1 sky  staff   11  3 20 08:04 current -> 11.0.2-open
```

### graalvm 20.3.5.r11 (x86_64)

为了使用 quarkus，安装 graalvm 20 版本，由于 graalvm 暂时没有 m1 可用的 arm64 版本，因此只能安装 x86_64 版本：

```bash
sdk install java 20.3.5.r11-grl
```

检查安装后的 java 设置：

```bash
$ which java                     
/Users/sky/.sdkman/candidates/java/20.3.5.r11-grl/bin/java

$ java --version
openjdk 11.0.14 2022-01-18
OpenJDK Runtime Environment GraalVM CE 20.3.5 (build 11.0.14+9-jvmci-20.3-b28)
OpenJDK 64-Bit Server VM GraalVM CE 20.3.5 (build 11.0.14+9-jvmci-20.3-b28, mixed mode, sharing)

$ env | grep JAVA_HOME
JAVA_HOME=/Users/sky/.sdkman/candidates/java/20.3.5.r11-grl
```



### zulu 11.0.14 (arm64)

类似的方式安装 zulu arm64 版本，zulu 是对 macos + arm64 支持比较好的 jdk，推荐作为 m1 的原生 java sdk：

```bash
$ sdk install java 11.0.14-zulu

Downloading: java 11.0.14-zulu

In progress...

##################################################################################################################################################### 100.0%

Repackaging Java 11.0.14-zulu...

Done repackaging...

Installing: java 11.0.14-zulu
Done installing!

Do you want java 11.0.14-zulu to be set as default? (Y/n): y

Setting java 11.0.14-zulu as default.
```

但特别注意，如果开启了 rosetta2 兼容模式，则会安装 x86_64 版本，而不是我们期望的 arm64 版本。

删除已经安装的 x86_64 版本的zulu jdk，特别注意要删除已经下载的 sdk 缓存文件，不然下次安装时会报告本地已经有文件而跳过下载过程。由于本地的是之前下载的  x86_64 版本，因此会导致无法安装 arm64 版本，必须删除本地缓存目录 `~/.sdkman/archives` 下对应的安装文件：

```bash
# 删除已经安装的 x86_64 版本的zulu jdk
$ sdk uninstall java 11.0.14-zulu   

# 删除已经下载的 java-11.0.14-zulu.zip 文件
$ ls ~/.sdkman/archives
java-11.0.14-zulu.zip   java-11.0.2-open.zip    java-20.3.5.r11-grl.zip maven-3.8.5.zip
$ rm ~/.sdkman/archives/java-11.0.14-zulu.zip 
```

备注：下载的安装文件不区分是否是 rosetta2 兼容模式，x86_64 和 arm64 下安装文件名是相同的。

如果要安装 arm64 版本，则需要关闭  rosetta2 兼容模式。`vi ~/.sdkman/etc/config`:

```properties
sdkman_rosetta2_compatible=true	# 修改这里为 false 关闭 rosetta2 兼容模式
```

修改后在当前终端中执行下面的命令立即更新：

```bash
source "/Users/sky/.sdkman/bin/sdkman-init.sh"
```

再次安装即可：

```bash
sdk install java 11.0.14-zulu  

Downloading: java 11.0.14-zulu

In progress...

##################################################################################################################################################### 100.0%

Repackaging Java 11.0.14-zulu...

Done repackaging...

Installing: java 11.0.14-zulu
Done installing!


Setting java 11.0.14-zulu as default.
```

还是需要执行下面的命令立即更新：

```bash
source "/Users/sky/.sdkman/bin/sdkman-init.sh"
```

然后检查安装后的 java 设置：

```bash
$ which java                                    
/Users/sky/.sdkman/candidates/java/current/bin/java

$ env | grep JAVA_HOME                          
JAVA_HOME=/Users/sky/.sdkman/candidates/java/current

$ java --version                                
openjdk 11.0.14 2022-01-18 LTS
OpenJDK Runtime Environment Zulu11.54+23-CA (build 11.0.14+9-LTS)
OpenJDK 64-Bit Server VM Zulu11.54+23-CA (build 11.0.14+9-LTS, mixed mode)
```

### maven

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

查看当前安装好的 java sdk ：

```bash
$ sdk list java | grep installed

               |     | 20.3.5.r11   | grl     | installed  | 20.3.5.r11-grl      
               |     | 11.0.2       | open    | installed  | 11.0.2-open         
               | >>> | 11.0.14      | zulu    | installed  | 11.0.14-zulu 
```

对比 `mvn --version` 在不同 java sdk 下的 输出。 在 openjdk x86_64 下：

```bash
$ sdk use java 11.0.2-open
$ mvn --version
Apache Maven 3.8.5 (3599d3414f046de2324203b78ddcf9b5e4388aa0)
Maven home: /Users/sky/.sdkman/candidates/maven/current
Java version: 11.0.2, vendor: Oracle Corporation, runtime: /Users/sky/.sdkman/candidates/java/11.0.2-open
Default locale: zh_CN_#Hans, platform encoding: UTF-8
OS name: "mac os x", version: "10.16", arch: "x86_64", family: "mac"

$ env | grep MAVEN_HOME
MAVEN_HOME=/Users/sky/.sdkman/candidates/maven/current
```

在 graalvm x86_64 下：

```bash
$ sdk use java 20.3.5.r11-grl
$ mvn --version
Apache Maven 3.8.5 (3599d3414f046de2324203b78ddcf9b5e4388aa0)
Maven home: /Users/sky/.sdkman/candidates/maven/current
Java version: 11.0.14, vendor: GraalVM Community, runtime: /Users/sky/.sdkman/candidates/java/20.3.5.r11-grl
Default locale: zh_CN_#Hans, platform encoding: UTF-8
OS name: "mac os x", version: "12.3", arch: "x86_64", family: "mac"
```

在 zulu arm64 下：

```bash
$ sdk use java 11.0.14-zulu
$ mvn --version
Apache Maven 3.8.5 (3599d3414f046de2324203b78ddcf9b5e4388aa0)
Maven home: /Users/sky/.sdkman/candidates/maven/current
Java version: 11.0.14, vendor: Azul Systems, Inc., runtime: /Users/sky/.sdkman/candidates/java/11.0.14-zulu/zulu-11.jdk/Contents/Home
Default locale: zh_CN_#Hans, platform encoding: UTF-8
OS name: "mac os x", version: "12.3", arch: "aarch64", family: "mac"
```

注意： zulu arm64 下 maven 的输出中 arch 终于改为 "aarch64" ，而不是 "x86_64"。

这个方法也可以用来快速检查当前 java sdk 是  "x86_64" 还是 "aarch64" （arm64）版本。


