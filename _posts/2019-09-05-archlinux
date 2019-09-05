---
layout: post
title: hug the manjaro(archlinux)
date: 2019-09-05
---

# Install Mnajaro
×manjaro×被称为最好用的linux，之前被centos搞得头大，因为centos比较×稳定×的属性，以至于软件源仓库内的包非常老。为了将一个小小的*Geant4*给装上去。
前面的required dependency安装非常费劲。因为软件仓库比较老，而*geant4*的依赖又比较新，所以需要四处寻找不同的仓库，此处需要大力表扬这个[软件包列表](pkgs.org).
有的软件包找不到还要自己手动编译，增加了很多工作量

之前发现*archlinux*很难用，所以没有上手，不过*manjaro*确实很不错，感觉安装比ubuntu还要舒服。在安装过程中还是有一些问题，所以记录一下。

## u盘制作
首先得下载一个镜像，*manjaro*官网很贴心的给出了许多不同种类桌面的镜像，我选择了一个轻量级桌面xfce，对应的[iso镜像](https://www.manjaro.org/download/xfce/)。

制作u盘镜像这个步骤在官网上有[介绍](https://manjaro.org/support/firststeps/#making-a-live-system)，我选择在windows下制作这个镜像，说明中特地
强调用*dd*模式写入，所以×不要×妄图使用windows的各种解压手段将镜像解压至u盘，因为根本不可能成功的(亲身经历的教训)。linux下也可以用命令行制作镜像，此时
需要的就是*dd*命令可以直接写。windows就不一样了，照着说明下载了rufus软件，不过这个软件很好，写u盘的速度可比那个ultraiso快了不知多少倍。

## 选择u盘启动
u盘插进电脑usb接口，然后重启电脑，进入bios(不同电脑不一样，我的是按del，典型华硕主板进入bios操作)，随后在启动选项就可以看到能够启动的选项，我的华硕主板
支持UEFI启动，很贴心的显示×UEFI：AI MASS STORAGE×很显然是那个u盘了，调整了盘符顺序，选择这个优先启动。保存设置重启

## 安装
安装过程还是很easy的，不过在选择partition这个步骤可能有点头疼。
+ 如果你的电脑只有一个硬盘，而且装了windows，那么界面会有四个选项，其中第一个是install alongside，就是可以和windows装在一起，感觉是寄生在windows磁盘里了。
+ 当然可以在windows下提前压缩一个盘出来，选择安装在那个partition
+ 如果硬盘空无一物，直接安装在整个disk上就可以了
+ 还有自定义的分区安装，没试过

## 配置
配置源为中国境内
```
sudo pacman-mirrors -c China
sudo pacman -Syy
```
[配置archlinuxcn](https://mirrors.tuna.tsinghua.edu.cn/help/archlinuxcn/)
[配置archlinux](https://mirrors.tuna.tsinghua.edu.cn/help/archlinux/)
配置AUR源，首先做这个[工作](https://mirrors.tuna.tsinghua.edu.cn/help/AUR/),随后按下面安装yaourt并更新
```
sudo pacman -S yaourt
sudo yaourt -Syy
```
之后安装输入法之类都行，尤其是AUR仓库中有wechat和qq，可以用yaourt安装，前提得把AUR源配置完。

# FAQ
## 用U盘安装过程一直失败，报错
可以考虑你有没有用最新的版本，之前用17版，死活安装不成功，报错partition无法创建之类的

## 输入法fcitx安装之后始终没有打出汉字或者切换输入法
首先检查fcitx是否启动，其次看有没有添加进pinyin或者googlepinyin输入法，之后将系统重启，看是否解决问题。
