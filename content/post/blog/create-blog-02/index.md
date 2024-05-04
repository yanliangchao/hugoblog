---
author: Alex Yan
title: 博客搭建记录 《二》
date: 2024-05-04T22:28:02+08:00
description: 使用 cloudflare vercel 部署博客
tags:
  - blog
  - vercel
categories:
  - log
image: create-blog-02.jpg
aliases:
  - create-blog-2
---
# 环境准备
1. 阿里云购买一个域名
2. 注册 [Cloudflare](https://dash.cloudflare.com/) 、[Vercel](https://vercel.com/) 和[GitHub](https://github.com/) 等网站

# 上传代码到Github
1. 在GitHub上新建一个博客项目
2. 本地blog内执行以下命令绑定到GitHub仓库
```shell
git init
git remote add origin <远程仓库的URL>
```
3. 本地blog内执行以下命令将blog代码同步到GitHub仓库
```shell
git add .
git commit -m "message"
git push origin main
```
# 部署项目到Vercel
1. 进入我的项目，新建一个项目
![[index-20240504222753.png]](index-20240504222753.png)
2. 从GitHub仓库导入项目
> 第一次使用要将项目从GitHub添加进来

![[index-20240504223519.png]](index-20240504223519.png)
> 这里选择添加的项目

![[index-20240504223631.png]](index-20240504223631.png)
> 添加成功后如下

![[index-20240504223852.png]](index-20240504223852.png)
3. 部署项目
> 点击上图的Import按钮
> 设置以下部署命令
![[index-20240504224548.png]](index-20240504224548.png)
> 环境变量设置hugo版本和你本地版本一致
![[index-20240504224659.png]](index-20240504224659.png)
> 点击Deploy，等待部署成功
![[index-20240504224803.png]](index-20240504224803.png)
4. 部署成功后的截图
> 部署成功后，Vercel会自动给你生成一个域名，但此域名现在只能通过科学方式访问。所以我们需要通过Cloudflare将阿里云购买的域名绑定到Vercel中去。让我们不需要科学方式访问。
![[index-20240504225234.png]](index-20240504225234.png)
# [Cloudflare](https://dash.cloudflare.com/)解析阿里云域名
1. 登录到[Cloudflare](https://dash.cloudflare.com/) ,点击网站，点击添加站点
![[index-20240504231242.png]](index-20240504231242.png)
2. 输入阿里云申请的域名，点击继续
![[index-20240504231403.png]](index-20240504231403.png)
3. 一直下一步到检查，会生成两个DNS地址
![[index-20240504231607.png]](index-20240504231607.png)
4. 登录到阿里云的域名管理
![[index-20240504232236.png]](index-20240504232236.png)
5. 修改DNS为第3步得到的DNS地址
![[index-20240504232416.png]](index-20240504232416.png)


6. 直到Cloudflare 检查通过，则为成功！
# Vercel修改域名为阿里云域名
1. 在Vercel项目中点击Domains
![[index-20240504232556.png]](index-20240504232556.png)

2. 新增域名，会提示你配置CNAME解析记录
![[index-20240504232813.png]](index-20240504232813.png)
3. 在Cloudflare添加这条解析记录
![[index-20240504232933.png]](index-20240504232933.png)
![[index-20240504233023.png]](index-20240504233023.png)
4. 直到Vercel验证通过，就可以通过这个域名访问Blog了。