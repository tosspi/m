---
title: "Notion设置中文"
date: 2022-03-23T10:56:44+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
# Notion设置中文
Notion目前没有中文界面，于是，便有动手能力强的大佬决定自己解决这个问题。目前有两种汉化方案：网页版汉化、客户端汉化。
网页版汉化：利用Chrome或Edge等浏览器使用油猴插件，安装脚本实现，插件：[NotionEnhancer](https://greasyfork.org/zh-CN/scripts/409695-notionenhancer)
客户端汉化：支持Windows、Mac以及安卓，详情见Github：[Notion-zh_CN](https://github.com/Reamd7/notion-zh_CN)
据说中文界面目前正在测试，估计中文界面已经快要到来了。
Mac端：
1、打开Finder,应用程序，右键Notion，显示应用包内容，打开Notion.app\Contents\Resources\app\renderer\
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/notion1.png)
2、将下载的notion-zh_CN.js移动到此目录。
3、编辑preload.js，在最后一行加上如下代码：
```
require("./notion-zh_CN")
```
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/notion2.png)
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/notion3.png)
4、最后重启 Notion，享受中文界面吧。
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/notion4.png)

## 最后
目前没有其他PC先写个Mac的吧，其他客户端可以到[GitHub](https://github.com/Reamd7/notion-zh_CN)看一下，教程很详细.
刚开始摸索Notion，以后再有其他的会继续编辑.