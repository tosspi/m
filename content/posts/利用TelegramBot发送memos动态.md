---
title: "利用TelegramBot发送memos动态"
date: 2023-08-26T13:55:10+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---

![23826-0](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-0.png)

今天更新了Memos，发现可以用TelegramBot发动态，于是就开始搞起来了。

```
需要准备工作：
1、建一个TelegramBot.
2、获取TelegramBot的Token.
3、获取Telegram的UserID.
```
## 新建一个TelegramBot
搜索[@BotFather](https://t.me/BotFather)

输入`/newbot`开始新建Bot

![23826-1](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-1.png)


最后出项Token（图片中的HTTP API就是）就OK了

![23826-2](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-2.png)

## 获取Telegram UserID

搜索[@userinfobot](https://t.me/userinfobot) 输入`/start`就出现了我们需要的Telegram UserID

![23826-3](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-3.png)

## 设置Memos
1.回到Memos，使用管理员登入，在`设置-系统`中的`Telegram机器人Token`输入我们获取到的TelegramBot Token保存.

![23826-4](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-4.png)

2.在`设置-偏好设置`中`Telegram UserID`中输入我们获取到的ID，保存，到这几基本上就大功告成了，测试一下。
![23826-5](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-5.png)
![23826-6](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-6.png)
![23826-0](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23826-0.png)



>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>