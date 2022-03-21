---
title: "VisualVM"
linkTitle: "VisualVM"
weight: 100
date: 2022-03-21
description: >
  VisualVM提供可视化的界面来查看Java应用程序的详细信息
---



## 安装

### 使用 sdkman 安装VisualVM

```bash
$ sdk install visualvm         

Downloading: visualvm 2.1.2

In progress...

######################################################################### 100.0%######################################################################### 100.0%

Installing: visualvm 2.1.2
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/org-graalvm-visualvm-lib-profiler.jar
          No such file or directory
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/update_tracking/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/update_tracking/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/update_tracking/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/locale/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/locale/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/locale/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/ext/locale/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/ext/locale/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/ext/locale/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/ext/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/ext/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/modules/ext/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/windows/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/windows/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/windows/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/windows-amd64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/windows-amd64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/windows-amd64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-sparcv9/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-sparcv9/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-sparcv9/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-sparc/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-sparc/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-sparc/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-i386/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-i386/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-i386/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-amd64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-amd64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/solaris-amd64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/mac/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/mac/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/mac/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-arm/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-arm/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-arm/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-arm-vfp-hflt/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-arm-vfp-hflt/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-arm-vfp-hflt/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-amd64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-amd64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-amd64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-aarch64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-aarch64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/linux-aarch64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk16/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/windows/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/windows/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/windows/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/windows-amd64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/windows-amd64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/windows-amd64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-sparcv9/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-sparcv9/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-sparcv9/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-sparc/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-sparc/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-sparc/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-i386/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-i386/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-i386/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-amd64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-amd64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/solaris-amd64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/mac/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/mac/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/mac/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/linux/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/linux/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/linux/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/linux-amd64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/linux-amd64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/linux-amd64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/jdk15/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/deployed/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/lib/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/core/locale/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/core/locale/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/core/locale/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/core/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/core/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/core/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/config/Modules/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/config/Modules/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/config/Modules/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/config/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/config/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/visualvm/config/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/update_tracking/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/update_tracking/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/update_tracking/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/x86/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/x86/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/x86/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/i386/linux/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/i386/linux/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/i386/linux/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/i386/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/i386/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/i386/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/amd64/linux/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/amd64/linux/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/amd64/linux/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/amd64/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/amd64/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/amd64/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/lib/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/ext/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/ext/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/ext/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/modules/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/lib/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/lib/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/lib/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/core/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/core/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/core/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/Modules/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/Modules/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/Modules/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/ModuleAutoDeps/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/ModuleAutoDeps/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/ModuleAutoDeps/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/config/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/platform/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/etc/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/etc/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/etc/
warning:  cannot set modif./access times for /Users/sky/.sdkman/tmp/out/visualvm_212/bin/
          No such file or directory
warning:  cannot set permissions for /Users/sky/.sdkman/tmp/out/visualvm_212/bin/
          No such file or directory
warning:  set times/attribs failed for /Users/sky/.sdkman/tmp/out/visualvm_212/bin/
mv: /Users/sky/.sdkman/candidates/visualvm/2.1.2 is not a directory
Done installing!


Setting visualvm 2.1.2 as default.
```

再安装一次，成功了：

```bashfd
$ sdk install visualvm

Found a previously downloaded visualvm 2.1.2 archive. Not downloading it again...


Installing: visualvm 2.1.2
Done installing!

Do you want visualvm 2.1.2 to be set as default? (Y/n): Y

Setting visualvm 2.1.2 as default.
```





```bash
jvisualvm --version
The operation couldn’t be completed. Unable to locate a Java Runtime that supports jvisualvm.
Please visit http://www.java.com for information on installing Java.

➜  ~ which jvisualvm 
/usr/bin/jvisualvm

$ sudo rm /usr/bin/jvisualvm   
Password:
Sorry, try again.
Password:
Sorry, try again.
Password:
override rwxr-xr-x root/wheel restricted,compressed for /usr/bin/jvisualvm? y
rm: /usr/bin/jvisualvm: Operation not permitted
```





## 配置

TBD







