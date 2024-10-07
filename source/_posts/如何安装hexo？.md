---
title: 如何安装hexo？
cover: /2024/10/07/如何安装hexo？/封面.jpg
coverWidth: 1920
coverHeight: 1080
date: 2024-10-07 18:09:40
categories: 个人随笔
tags: hexo
---
由于我又又又换了电脑来写博客，所以又得重新配置环境了.
感觉环境配置真的是太太太痛苦了，趁着我还有记忆，还是记录一下过程吧
## 安装git及node.js
可以用任意喜欢的方式安装，参考网址：
https://hexo.io/zh-cn/docs/
这里需要注意的是，如果出现了node.js安装完毕但是npm超时的情况，需要将npm更改为镜像网站，powershell中输入：
```npm config set registry https://registry.npmmirror.com```
## 从git上拉取我的博客仓库
出现的问题是：明明开了加速器但依旧超时
可能的原因是：有时网络较慢或服务器响应延迟可能导致数据接收中断
解决的方式是：
```
git config --global http.postBuffer 157286400
git config --global http.lowSpeedLimit 0
git config --global http.lowSpeedTime 99999
```
## 运行hexo时报错“因为在此系统上禁止运行脚本”
先查看当前系统的运行策略,在powershell中运行以下命令：
```Get-ExecutionPolicy```

然后更改执行策略，执行策略可以设置为以下几种模式：
1. Restricted：不允许运行任何脚本（默认策略）。
2. AllSigned：只允许运行由可信发布者签名的脚本。
3. RemoteSigned：允许运行本地脚本，但从互联网下载的脚本必须签名。
4. Unrestricted：允许运行所有脚本，但会警告你从互联网下载的脚本。

一般而言建议使用RemoteSigned，在powershell中运行以下命令：
```Set-ExecutionPolicy RemoteSigned -Scope CurrentUser```

目前遇到的问题就是这些，如果后面还有问题的话，还会继续更新