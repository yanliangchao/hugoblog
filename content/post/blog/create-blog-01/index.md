---
author: Alex Yan
title: 博客搭建记录 《一》
description: 使用Hugo搭建博客 - 准备工作
date: 2024-04-05T22:28:02+08:00
#draft: 
tags: [
    "blog"
]
categories: [
    "log",
]
image: "create-blog-01.jpg"
aliases: ["create-blog-1"]
---

# 下载安装Hugo

1. 访问[Hugo Github仓库](https://github.com/gohugoio/hugo/releases)， 选择合适的`extended`版本下载
![alt text](img/blog/blog-image.png)
2. 解压到本地目录
![alt text](img/blog/blog-image-1.png)
3. 配置环境变量并测试
![alt text](img/blog/blog-image-2.png)

# 使用Hugo创建Blog网站

1. 在本地打开PowerShell使用Hugo命令创建Blog网站
```shell
hugo new site MyBlog
```
* MyBlog 是文件夹名称，可以自己换。
2. 进入创建好的MyBlog目录，能看到如下生成的文件
![alt text](img/blog/blog-image-3.png)
3. 使用Hugo命令创建文章, 例如创建一个About页面
```shell
hugo new about.md
```
* 它会在content目录下面创建一个about.md的TOML文件

![alt text](img/blog/blog-image-5.png)
![alt text](img/blog/blog-image-6.png)
3. 启动Hugo服务
```shell
hugo server
```
![alt text](img/blog/blog-image-4.png)
4. 访问步骤3中hugo启动的地址端口,如下则成功！

![alt text](img/blog/blog-image-7.png)
# 导入主题
1. 你可以在[Hugo官网](https://themes.gohugo.io/)中寻找喜欢的主题，我这里使用的是[hugo-theme-stack](https://github.com/CaiJimmy/hugo-theme-stack)。
![alt text](img/blog/blog-image-8.png)
2. 进入[hugo-theme-stack](https://github.com/CaiJimmy/hugo-theme-stack)的releases，下载源码包
![alt text](img/blog/blog-image-9.png)
3. 将源码包解压到上述创建的项目中的`themes`目录中,目录结构为
```
MyBlog/
│
├── ···/
│   ├── ···
│   └── ···
│
├── ···/
│   └── ···
│
└── themes/
    │
    └── hugo-theme-stack/
        ├── ···
        └── ···
```
4. 配置主题模板
* 删除`MyBlog/hugo.toml`
* 复制`MyBlog/themes/hugo-theme-stack/exampleSite/hugo.yaml`到`MyBlog/hugo.yaml`中
* 复制`MyBlog/themes/hugo-theme-stack/exampleSite/content`到`MyBlog/content`中
5. 重新启动`hugo server`,并再次访问浏览器，模板能正确访问到
![alt text](img/blog/blog-image-10.png)


> 至此，Hugo搭建博客并导入模板已完成！！！
