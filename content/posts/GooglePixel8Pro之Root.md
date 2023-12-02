---
title: "Google Pixel8 Pro之ROOT"
date: 2023-12-02T07:54:25+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---

![1701477027262](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701477027262.jpg)

 入手了Google Pixel8 Pro,开始了折腾之路，首先就是ROOT

 ## 电脑上配置ADB环境及安装Google USB驱动程序

 1.下载ADB工具，可以到Android开发者网站下载[SDK平台工具页面](https://developer.android.com/studio/releases/platform-tools?hl=zh-cn)
![1701480039554](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701480039554.jpg)


 2.下载Google USB驱动程序，从Android开发者网站下载[Google USB Driver](https://developer.android.com/studio/run/win-usb?hl=zh-cn)
![1701480039935](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701480039935.jpg)

 ## 手机上打开ADB开关，解锁Bootloader

 1.打开USB调试开关
 2.关闭系统自动更新开关
 3.打开OEM解锁开关
 ![1701480141217](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701480141217.jpg)

 完成以上操作后，将手机插到电脑上，然后在手机弹出的窗口中，勾选「一律允许使用这台计算机进行调试」，然后点击允许

 然后在下载的「Platform-tools」文件夹下打开CMD命令行，输入

 ```
 adb reboot bootloader
 ```

 进入Bootloader菜单，再执行以下命令，就会解锁Bootloader

 ```
 fastboot flashing unlock
 ```

 ## 下载所需的出厂镜像
将手机更新到最新的系统，然后去[Google Play Services](https://developers.google.com/android/images?hl=zh-cn)下载对应的最新的出场镜像并解压，得到init_boot.img文件，将其传输到手机。

![1701478140351](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701478140351.jpg)

![1701478252285](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701478252285.jpg)

 ## 安装Magisk APP

去Masgisk的[Github项目页面](https://github.com/topjohnwu/Magisk)下载最新的版本安装包，并安装。

![1701478425053](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701478425053.jpg)


 ## 修补镜像

 在手机上安装好最新版本的 Magisk 之后，我们就可以用它来修补之前在完整系统镜像中找到的 init_boot.img 启动文件了。

在Pixel上的Magisk.app中，点击最顶上Magisk旁边的安装，选择「选择并修复一个文件」，点击并选中刚刚上传得到手机的init_boot.img文件，然后点击开始，Magisk就会自动开始修补，并将处理好的新的init_boot.img文件保存在根目录的Download文件中。

![1701479133363](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701479133363.jpg)

当magisk提示All Done修补完成后，将修补完成后的init_boot.img文件提取出来，传输到电脑上。

![1701479164394](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/1701479164394.jpg)


 ## 修补boot.img和刷写

 接下来就是修后一步了。

 执行` adb reboot bootloader`进入到Bootloader模式，输入以下代码刷入修补好的init_boot.img文件。

 ```
 fastboot flash init_boot /目录/masgisk_patched-*****_******.img
 ```

 完成后输入`fastboot reboot`重启手机。

 到此就root完成了。

 PS.
 *1.刷写命令中目录及文件名称要根据自己实际情况进行修改，也可以直接将修补好的init_boot.img文件放入fastboot工具的目录下，输入fastboot flash init_boot masgisk_patched-*****_******.img`刷入。*
 *2.因为我已经ROOT过了，当时操作没有记录，所以过程可能有点漏，*




<br>

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>
