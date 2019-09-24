---
layout: post
title: build personal blog
date: 2019-09-23
---
## choose a suitable blog

+ [Hero](https://hexo.io/zh-cn/docs/index.html)
+ [MkDoc]()

## Hero blog

### npm and nvm

当直接使用
```
npm install -g hexo-cli
```
极可能出现EACCES错误，可以
[安装nvm](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)
并重新安装npm,nodejs解决

可以发现实际上**HEXO**被安装到
```
~/.nvm/versions/node/v12.10.0/bin/hexo 
->
~/.nvm/versions/node/v12.10.0/lib/node_modules/hexo-cli/bin/hexo
```
### latex支持
发现[简书](https://www.jianshu.com/p/68e6f82d88b7)提供了一个很好的解决方案

+ 安装kramed
```
npm uninstall hexo-renderer-marked --save
npm install hexo-renderer-kramed --save
```
+ 更改配置文件，此处待我仔细研究，用到了正则表达式，直接参考上面简书内链接
+ 然后需要使用mathjax，要在themes中修改配置文件，默认的**landscape^^并没有这个选项，所以只好
转投**next**主题，在官网上按照[说明](http://theme-next.iissnan.com/getting-started.html)安装
+ 修改根目录下**_config.yml**的选项**themes: next**,修改**next**文件夹下的**_config.yml**中的选项**mathjax: enable:true**

### 分类支持
参考了知乎上的一个回答，使用了categories,目前还没有实际使用
### 快速部署
网页上很多是使用github部署，官网上也给出了其他的部署方案，我在这里用到了[rsync](https://hexo.io/docs/other-deployments#Rsync)
的部署方案。

```
deploy:
  type: rsync
  host: parity
  user: greatofdream
  root: /var/www/physics
```
此处远程服务器parity在本地有greatofdream用户的ssh公钥，可以直接ssh登录

```
hexo g #产生文件
hexo d #部署文件
```
