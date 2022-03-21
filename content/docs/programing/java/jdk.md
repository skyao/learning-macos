---
title: "JDK"
linkTitle: "JDK"
weight: 10
date: 2022-03-08
description: >
  JDK
---

在 m1 macbook 上安装 jdk 相对会有更多的麻烦，因为 m1 的 cpu 架构不再时传统的 x86_64 ，而是 aarch64 (arm64)。

## 安装 JAVA SDK （for M1）

暂时使用 jdk 11，在 m1 上需要安装多个版本：

- zuul jdk : arm64 版本，作为原生版本使用
- openjdk 11: x64 版本
- graalvm 11: x64 版本，学习 quarks / spring native 使用。（备注：graalvm 目前还没有 m1 原生支持）

### zulu 11.0.14 (arm64)

zulu 是对 macos + arm64 支持比较好的 jdk，推荐作为 m1 的原生 java sdk：

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

### openjdk 11 （x86_64）

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

## maven

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

## 自动切换JDK

通常使用场景时默认使用一个 jdk，然后在某些目录下需要使用其他的 jdk。例如我在 m1 macbook 下默认使用 aarch64 （arm64） 的 zulu jdk，但在某些特殊项目如 dapr 的 java-sdk 项目下，必须使用 x86_64 的 openjdk。

sdkman 提供在进入某些项目或目录时自动切换 sdk 的功能。

`vi ~/.sdkman/etc/config` 打开 sdkman 的配置文件，设置 `sdkman_auto_env` 为true:

```properties
sdkman_auto_env=true
```

`source "~/.sdkman/bin/sdkman-init.sh"` 让配置生效。然后：

```bash
# 用 mvn --version 命令查看 arch，默认用的是 zulu jdk，因此是 aarch64
mvn --version
OS name: "mac os x", version: "12.3", arch: "aarch64", family: "mac"

# 进入需要设置的目录
$ cd word/code/dapr/java-sdk

# 切换到 x86-64 的 openjdk 
$ sdk use java 11.0.2-open
# 用 mvn --version 命令查看 arch，此时是 x86_64
$ mvn --version
OS name: "mac os x", version: "10.16", arch: "x86_64", family: "mac"

# 初始化sdk env，sdkman 会记录下当前使用的 jdk 到当前目录下的 .sdkmanrc 文件
$ sdk env init
.sdkmanrc created.
```

`vi .sdkmanrc` 查看内容：

```properties
# Enable auto-env through the sdkman_auto_env config
# Add key=value pairs of SDKs to use below
java=11.0.2-open
```

在终端中尝试进入和退出项目所在目录：

```bash
$ cd ..      
Restored java version to 11.0.14-zulu (default)

$ cd java-sdk 
Using java version 11.0.2-open in this shell.

# 在子目录中跳转时不会触发自动切换的，也就是目录下的所有子目录都将维持这个sdk设置
$ cd sdk-autogen
```

## 参考文档

- [Usage - SDKMAN! the Software Development Kit Manager](https://sdkman.io/usage)



