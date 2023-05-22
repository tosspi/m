---
title: "解决Windows10打开Microsoft Store出错问题"
date: 2022-03-05T10:56:44+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
# 解决Windows10打开Microsoft Store出错问题
看到Mind Maps Pro、Penbook限免，想白嫖一波，可是打开Microsoft Store出现如下报错：
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/1.png)
经过一番折腾，终于找到了解决办法：
首先打开控制面板选择网络和Internet
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/2.png)
选择『Internet选项』
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/3.png)
点击『高级』，然后把下边的"使用SSL 3.0"、"使用 TLS1.0"、"使用 TLS1.1"、"使用 TLS1.2"、"使用 TLS1.3(实验性)"全部勾选
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/4.png)
再此打开Microsoft Store，完美解决
![](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/5.png)

## 最后
前几天碰到一台电脑，在登入Office 365的时候老是出现错误，无法打开登录页面，估计用这个方法可能也可以解决，没有尝试，等下次碰到试一下。