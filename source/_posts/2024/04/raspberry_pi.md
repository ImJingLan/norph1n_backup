---
title: 树莓派4B烧录CentOS并且使用宝塔搭建博客
categories:
  - 其他
copyright: BY-NC-SA
date: 2024-05-01 20:52:04
tags:
cover:
---

# 前言

之前朋友借了我一块树莓派 4B 给我捣鼓，还帮我建了个博客。但是由于不会维护导致最后那个博客荒废了，树莓派也在家里吃灰。学校信息课学到了 Arduino 开发板，就突然心血来潮想着捣鼓一下树莓派，把网站建起来什么的。现在网站建起来了，就写一篇博客防止遗忘。

# 烧录 CentOS

用到的东西：读卡器，TF 卡

首先先把要安装的系统[下载](https://mirrors.tuna.tsinghua.edu.cn/ubuntu-cdimage/releases/jammy/release/ubuntu-22.04.4-preinstalled-desktop-arm64%2Braspi.img.xz)下来

![点击NEXT][1]

#在树莓派上进行操作 ##登录树莓派

烧录完毕后，将 TF 卡插回树莓派，我们就可以进行下一步了

首先我们要知道树莓派的 ip

知道 ip 以后，Win+R 然后输入 cmd 打开命令提示符

![cmd.png][2]

这里我们要用 ssh 对树莓派进行一个录的登

```bash
ssh root@ip
```

密码：`centos`

![屏幕截图 2024-03-29 232032.png][3]

这样就登好了

## 安装宝塔

接着就要安装[宝塔](https://www.bt.cn/new/download.html)

![屏幕截图 2024-03-29 232032.png][4]

复制 CentOS 安装脚本到终端，开始下载

```bash
yum install -y wget && wget -O install.sh https://download.bt.cn/install/install_6.0.sh && sh install.sh ed8484bec
```

安装完毕后输入 14 查看面板后台

![屏幕截图 2024-04-10 231956.png][5]

## 配置环境

进入后台，注册宝塔账号，安装 Nginx MySQL PHP（我的是 8.2.16）

这需要等待一段时间

## 安装实例

接下来就是配置网站了

在宝塔内网面板地址中第二项**网站**中输入该站点所链接的域名

## SSL 证书申请

点击相应的网站名>>SSL>>Let's Encrypt
根据指示添加证书即可
![屏幕截图 2024-04-10 234922.png][6]

[1]: 1947472092.png
[2]: 2553568203.png
[3]: 1391131277.png
[4]: 3216342165.png
[5]: 889479769.png
[6]: 2234084613.png
