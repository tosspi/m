---
title: "GooglePixel8Pro之电信开启VOLTE并设置5G"
date: 2023-12-04T08:08:43+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
![1701651809076](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701651809076.jpg)

其实不ROOT也可以开启VoLTE,与本次折腾使用的软件都是一样的，唯一的区别就是Shizuku的运行方式罢了。

1.首先下载Shizuku，并确保Shizuku服务已经正常运行。

![1701649838226](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701649838226.jpg)

2.前往Pixel IMS的[发行版](https://github.com/kyujin-cho/pixel-volte-patch/releases)页面下载并安装最新版，安装完成后启动Pixel IMS，会看到一个Shizuku接口调用的请求，选择总是允许；进入Pixel IMS主界面，选择电信卡，点击启用VoLTE,重启以后就可以看到SIM设置中的VoLTE选项开关了，到现在电信卡就可以正常使用4G网络了。

![1701649837711](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701649837711.jpg)

3.开启5G。下载[网络信号大师](https://play.google.com/store/apps/details?id=com.qtrun.QuickTest)：

![1701649246233](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701649246233.jpg)

3.1启动网络信号大师并授予Root权限。

3.2主界面右上角三点设置选择「强制功能」，然后选择「SIM 1」- 「NR MODE SETTING」- 「SA+NSA」

![1701649838880](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701649838880.jpg)

3.3重启手机即可获得5G网络支持。

4.在设置中会出现一个Vo5G,打开此开关，在通话时将不会调5G网络数据。

![1701650044985](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701650044985.jpg)



<br>

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>