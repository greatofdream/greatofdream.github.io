---
layout: post
title: "linux distribution CentOS install record"
date: 2019-8-16
---

## use minimal iso

the iso url is http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso

it was a stupid choice which took me about 5 hours to wait the source installation verified and failed at last.

## use dvd iso

the iso file size is about 4.3GB.([url](http://mirrors.tuna.tsinghua.edu.cn/centos/7.6.1810/isos/x86_64/CentOS-7-x86_64-DVD-1810.iso))

must use the ultraiso or other tools to write the iso into the U-disk.

+ Do not use the windows file explorer, just copy make no sense.
+ should assign the disk first
+ when creating the user(not root), if you add group and then check the administator, installation will give a bug and you only restart and do all things again.

## centos 中文输入法

```
ibus-setup
```

出现一个`gui`界面,在`preference`中添加语言，需要退出重新进入

## centos screen brightness

icon in the menu bar, which is charge management.

## openvpn requirement

+ tun/tap
```
modinfo tun
modprobe tun
lsmod |grep tun
```
+ openssl
```
yum install openssl-devel
```
+ lzo
```
yum install lzo-devel
```
+ libpam
```
yum install pam-devel
```
+ cmake
```
yum install cmake
```
+ cmocka

strange error and do not need to handle this error

[just need download a git repo](https://github.com/OpenVPN/openvpn/blob/master/INSTALL)you can find detail in the INSTALL instructions.

+ problem

 - cannot ping the ip in vpn network
 
 




