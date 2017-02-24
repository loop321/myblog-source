---
title: 筑巢于春
date: 2017-02-18 10:19:55
tags: ["hexo"]
categories: ["随笔"]
toc: true
---

> <h2 id="intro">前言</h2>早就想做一个博客，现在终于抽出精力做一个自己的小站。从此，在这里留下我远行的脚步。

<!-- more -->

### 萌动尝试，笃定信念
  在大学时接触到网络，断断续续的注册了百度、163、51等的博客，好奇过后就扔在一边。工作后尝试了cms、论坛、空间等入门的技术，刚毕业的前几年东奔西跑也没能停下来，静下心写写自己的感想。如今已毕业近10年，其中酸甜苦辣也都随时光流逝沉淀与心底。

![图1](2017-start/01.jpg)

------

> 心中总有一个念头，希望充实每一天，在某天回望过去，不会因虚度而悔恨。年后准备了域名空间，做一个简单的小站，记下工作和生活的点点滴滴。

### 搭建过程

#### 准备
- 【可选】域名([万网](https://wanwang.aliyun.com)|注册一个自己的域名)
- 【可选】空间(云服务、vps|也可以用githup，不用自己的空间)
- [githup帐号](https://githup.com/loop321)(注册githup)
- [hexo](https://hexo.io)(站点系统)
- 【可选】[nginx](http://nginx.org)(自己空间可以配合nginx使用)

本站采用：域名+云主机+githup+hexo+nginx

#### 搭建
1.注册域名
普通的cn、com域名费用每年几元到几百不等，也有免费的顶级域名： http://www.dot.tk/ （免费一年，到期后再操作续期，域名有最低访问要求）
域名解析到您的服务器上。

2.空间
国内主流的云服务器价格稍贵，国外的VPS很便宜但安全性稳定性不确定，直接用github不用银子。

3.githup
在 https://githup.com 上根据邮箱、用户名注册，并建立仓库(例如仓库名为:myblog)用以存放hexo生成的网站内容。同时生成根据githup的邮箱、用户名在服务器上配置（`git config --global user.name git用户名`、`git config --global user.mail git邮箱`）、生密钥（命令：`ssh-keygen -t rsa -C "your_email@youremail.com`）。

4.安装node.js、hexo
centos为例:
安装nodejs: `yum -y install nodejs`
安装hexo: `npm install hexo-cli -g`
建立网站目录: `mkdir -p /opt/myblog`
初始化hexo网站: `cd /opt/myblog`,`hexo init`,`npm install`
生成网站内容: `hexo g`

5.nginx
安装: yum install nginx (如果没有，需要到官网下载包进行安装)
修配配置并启动： 打开配置文件（每个系统路径可能不一样）`vi /etc/nginx/nginx.conf`
增加配置：

```
server {
        listen       80;
        server_name  your domains; 
        root /opt/myblog/public;
}

```

-----
> 至此一个简单的小站已经运行起来，hexo有很多插件和主题可以使用，后续更新。






