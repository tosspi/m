---
title: "GooglePixel8Pro之Root后每月系统更新"
date: 2023-12-11T10:45:31+08:00
draft: false
tags: ["折腾","Pixel"]
adjacentPost: true
readingBar: true
---

![1702262839656](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1702262839656.jpg)

## 准备
在Root后，就没有办法正常的通过系统OTA更新Google每月的安全更新了，那么就只能通过我们自己手动来更新了，开搞。

首先去完整的OTA镜像[Full OTA Images for Nexus and Pixel Devices](https://developers.google.cn/android/ota#husky)。

解压，使用编辑器打开`flash-all.bat` 这个文件。

![1702264896783](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1702264896783.jpg)

修改`fastboot -w update image-husky-uqla.231205.015.zip` 为 `fastboot update image-husky-uqla.231205.015.zip` 就是去掉"-w".

![1702262839647](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1702262839647.jpg)

## 更新

接下来就是执行"flash-all.bat"这个文件。

1.将手机链接到电脑，在adb文件夹按住"Shift"邮件，点击“在此处打开命令窗口”（CMD），然后输入`abd devices`查看手机是否成功连接。

2.重启手机到Bootloader,输入`abd reboot bootloader`.

3.双击“flash-all.bat”，等待跑完就可以了。

## 完成后恢复ROOT环境

更新完，root会被破坏，需要重新刷写Magisk，同[Google Pixel 8 Pro之ROOT](https://imum.me/posts/googlepixel8pro%E4%B9%8Broot/).

需要注意的是root过程中需要"boot.img"与"init_boot.img"文件应该是我们下载的完成OTA镜像中的。

![1702264896974](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1702264896974.jpg)


<br>

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>