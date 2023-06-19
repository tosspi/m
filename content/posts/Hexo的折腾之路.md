---
title: "Hexo的折腾之路"
date: 2021-09-21T10:56:44+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
![WX20220921-161133](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220921-161133.png)
2023.05.22更新
今天Hexo正式弃用了，现在换成Hugo了，采用了，GitHub仓库+Cloudflare Pages部署原先分成俩的博客正式合成一个。（过几天，新工厂搬家完成以后写一个全面拥抱Cloudflare Pages的文章）

## 前言
  折腾博客应该是从去年开始，具体时间忘记了，一开始是hexo+GitHub Pages，主题用过[Ayer](https://shen-yu.gitee.io/)、后来换成了[Butterfly](https://github.com/jerryc127/hexo-theme-butterfly) ,这里说一下butterfly确实不错，可以折腾的地方太多了。最后换成了本站这种样式[nexT](https://github.com/next-theme/hexo-theme-next),采用GitHub存储库+Vercel部属+Cloudflare加速。
![WX20220921-161626](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220921-161626.png)![WX20220921-161645](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220921-161645.png)
***这个是Ayer***
![1e0d7e6d6fb6a9863f2287fe8ba38e3c33e92951.jpg@942w_3201h_progressive](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/1e0d7e6d6fb6a9863f2287fe8ba38e3c33e92951.jpg@942w_3201h_progressive.webp)
***Butterfly***
## Hexo 安装环境搭建
  1.安装Git
  https://git-scm.com/
  2.安装Node.js
  https://nodejs.org/en/
## 安装Hexo 程序
运行安装命令：
`npm install -g hexo-cli`
查看版本以及验证是否安装成功：
`hexo v`
创建博客文件夹，进入文件夹内执行以下命令初始化Hexo环境（必须是空文件夹）：
` hexo init`

## 安装主题
1.获取主题的命令如下：
`npm install hexo-theme-next`
或者
`git clone https://github.com/next-theme/hexo-theme-next themes/next`
***注意使用npm获取主题不会在themes文件夹下拉取主题文件，此代码为next的主题获取方式***
2.将主题文件内的`_config.yml`重新命名为`_config.next.yml`并拷贝到博客文件夹下。
## 主题配置
1.更改博客文件夹下`_config.yml`
```
# Site
title: 折腾派 #博客的名称
subtitle: '生命不惜,折腾不止' #随便自己
description: ''
keywords:
author: Zhao   #作者
language: zh-CN   #语言
timezone: ''
```
切换为我们安装的主题
```
theme: next
```
2.修改博客文件夹下`_config.next.yml`
```
先欠着，过段时间再来添加
```
## Hexo常用命令
1.新建文章
`hexo new "文章名称" `
***生成的文件在`/博客文件夹/source/_posts/ `使用Markdown工具编辑既可***
2.新建页面
`hexo new page 页面名称 `
***生成的页面在`/博客文件夹/source/`下对应的文件夹内，可根据需要修改`index.md`文件。
3.生成博客页面文件
`hexo g`
4.运行服务（本地环境测试使用）
`hexo s`
***运行后浏览器输入 `localhost：4000`既可查看***
5.部属到GitHub Page
`hexo d`
6.清理缓存
`hexo c`
## git配置
1.切换到博客文件夹下输入以下命令配置用户名和邮箱：
```
git config --local user.name XXXXX     #用户名
git config --local user.email XXXXX@XXXXX   #邮箱
```
2.配置远程仓库
```
git remote add origin git@github.com:XXXX/XXXX.git
```
## 推送到GitHub仓库
  我使用的是VS Code，很方便
![WX20220921-165454](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220921-165454.png)
我的方案是将整个博客文件夹全部推送到GitHub仓库，然后利用vercel部属，这样方便换电脑的时候直接从远程仓库拉取就可以了。
**踩个坑，当我全部弄完推送GitHub的时候发现`node_modules`无法推送，折腾了一大圈才发现原因，git上传的时候忽略了`node_modules`，解决方法：**
博客文件夹下找到` .gitignore `文件，删除掉里边的你想要推送到远程库的文件夹/文件名既可
![WX20220921-170200](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220921-170200.png)
## 部属
  部属我选用的[Vercel](https://vercel.com/)部属，这个很简单就不详细描述了
![vercel-logotype-dark](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/vercel-logotype-dark.svg)
![WX20220921-170844](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220921-170844.png)

   当然还可以选择[Netlify](https://app.netlify.com/),我的另一个博客就是用Netlify部属的，当然采用的hugo+Netlify。
   ![WX20220921-171550](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220921-171550.png)
   Cloudflare这里就不多说了，同样简单。   






>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>