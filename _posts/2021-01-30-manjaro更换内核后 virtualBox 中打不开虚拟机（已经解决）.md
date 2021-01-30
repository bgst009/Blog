---
layout: post
title: manjaro更换内核后 virtualBox 中打不开虚拟机（已经解决）
categories: [备忘]
description:  manjaro更换内核
keywords: Linux, Manjaro
---
参考链接[^1]

# 问题描述

> 更换完5.9内核后 VirtualBox 提示 `Kernel driver not installed (rc=-1908) `

```bash
"The VirtualBox Linux kernel driver is either not loaded or not set up correctly. Please try setting it up again by executing

'/sbin/vboxconfig'

as root.

If your system has EFI Secure Boot enabled you may also need to sign the kernel modules (vboxdrv, vboxnetflt, vboxnetadp, vboxpci) before you can load them. Please see your Linux system's documentation for more information.

where: suplibOsInit what: 3 VERR_VM_DRIVER_NOT_INSTALLED (-1908) - The support driver is not installed. On linux, open returned ENOENT. "
```

# 解决办法
- 执行下面的指令然后查看输出

```bash
pacman -Qs linux
uname -a
```
- 在第一条指令执行完后查看与下列类似的输出,可以看到我以前安装的是5.4内核对应的modules

```bash
local/linux54-virtualbox-host-modules 6.1.16-3 (linux54-extramodules)

```
- 在第二条指令执行后查看可以发现现在的内核版本为5.9和上面的` (linux54-extramodules)`有所不同，然后尝试安装和59匹配的
```bash
 5.9.3-1-MANJARO 
```
- 执行命令 `pacman -S linux59-virtualbox-host-modules`,然后重启后就可以在Virtual Box正常打开虚拟机了

[^1]: [[SOLVED] Virtualbox failed to open virtual machine](https://bbs.archlinux.org/viewtopic.php?id=258955)