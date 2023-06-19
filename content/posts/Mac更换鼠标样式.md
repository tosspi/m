---
title: "Mac OS更换鼠标样式"
date: 2021-11-06T10:56:44+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
# 介绍

&emsp;&emsp;mac更换鼠标样式依靠mousecape实现，

[mousecape](https://github.com/alexzielenski/Mousecape)是Github上的一个项目，作者是[alexzielenski](https://github.com/alexzielenski)，

&emsp;&emsp;项目是用于修改Mac系统鼠标样式的，支持动态鼠标样式。

# mousecape使用

&emsp;&emsp;可以去[Github](https://github.com/alexzielenski/Mousecape/releases/tag/1813)下载，也可以从[这里下载](https://ibelife.cowtransfer.com/s/f6e5fd85dfe943)，下载解压后拖入Applications并安装一下帮助工具就好啦(因为我已经安装了，所以显示的是***Uninstall Helper Tool***)。

![help tool截图](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211110-162606.png)

# 添加鼠标样式

## 指针样式准备

&emsp;&emsp;鼠标样式可以自己制作采用图片的方式来制作，在此之前我们可以制作一些png格式的图片(可以用Photoshop之类的软件)，也可以自己下载一些已经制作好的鼠标指针，我是在[致美化](https://zhutix.com/tag/cursors/)下的，下载完解压，选用cur格式的。

![鼠标指针解压截图](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-111028.png)

## 制作并使用

&emsp;&emsp;依次点击左上角File👉🏻New Cape

![新建样式](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-111459.png)

&emsp;&emsp;然后会出现一个新的样式Unnamed，右键点击Edit

![添加样式2](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-111525.png)

&emsp;&emsp;在此页面可以修改名字、作者、文件名、版本号、Retina选项。

![新建样式2](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-111610.png)

> 这里解释一下Retina是什么，Retina是一种显示标准。不一定所有的Mac都是Retina屏，可以看一下关于本机的系统报告，硬件中显示器一栏由显示器类型，如果显示的是内建视网膜，说明是Retina屏。
>
> 这个时候就勾选Retina，但其实区别不大。
>
> Mac Retina [官方文档](https://support.apple.com/zh-cn/HT202471) 

&emsp;&emsp;填写好信息以后，右键选择New Cursor，也可以点击左下角『+』号添加

![新建样式](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-111643.png)

&emsp;&emsp;填写相关信息

![新建样式4](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-111704.png)

- cursor参数值的设定：
  1. 可以把样式文件拖到右下角虚线框里，如果有工夫可以把2x、5x、10x都填充了，提高鼠标放大后的清晰度。
  2. 然后Type可以看一下下文对指针样式的说明，这里的Arrow代表默认箭头。
  3. Frames代表帧数。
  4. HotSpot就是实际点击位置，为了确保我们点击不会有偏差，一般会设置在箭头`<-`的尖尖上或者移动箭头`<->`的中心。
  5. Size就是大小啦。

![新建样式](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-111752.png)

&emsp;&emsp;在拖完样式以后会看到有个小红点，然后修改HotSpot调整实际点击位置

![添加样式5](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-113902.png)

&emsp;&emsp;所有样式添加完成以后，右键点击Apply就可以看到鼠标样式已经更改。

![应用样式](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-114202.png)

## 取消鼠标指针修改

&emsp;&emsp;点击右上角Capes👉🏻Remove Cape就可以了

![取消样式修改](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211112-114211.png)

# 关于指针样式的一些说明

## Mac OS鼠标指针样式的官方文档

&emsp;&emsp;官方文档是稍微有一点小bug的，比如：

- 错别字 中文版文档：“当您选择图像中的句型(矩形)区域时，该光标会出现。”
- 不详尽 比如move系列是有斜对角方向的，官方文档没有写，而且样式也稍微有些不一样；可能还有其他指针样式的遗漏。

> [中文官方文档](https://support.apple.com/zh-cn/guide/mac-help/mh35695/10.13/mac/10.13)
>
> [英文官方文档](https://support.apple.com/en-au/guide/mac-help/mh35695/mac)

## mousecape的指针样式命名

&emsp;&emsp;mac系统的指针样式是稍微有一点小bug的，比如：

- 有一些样式会失效，比如制作替身、拖拽拷贝
- 有一些样式会闪烁，比如点击链接等手形指针



| mousecape命名 |                    解释                    |                             展示                             | 可用 |
| :-----------: | :----------------------------------------: | :----------------------------------------------------------: | :--: |
|     Alias     |                  制作替身                  | ![dde1ed13deb66e74f5c0996556c1da05](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/en_AU/dde1ed13deb66e74f5c0996556c1da05.png) |  ×   |
|     Arrow     |                  默认箭头                  | ![a0d5e859e5f2b01dbbf81dfc38a3a92f](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/a0d5e859e5f2b01dbbf81dfc38a3a92f.png) |  √   |
|     Busy      |                    null                    |                             null                             |  ×   |
|    Camera     |             可能是旧版的Camera             |                             null                             |  ×   |
|    Camera2    |               捕捉窗口或菜单               | ![a1d807299b5280d18764e80ef9803960](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/en_AU/a1d807299b5280d18764e80ef9803960.png) |  √   |
|   Cell系列    |                    null                    |                             null                             |  ×   |
|    Closed     |         并拢的手(详见mac官方文档)          | ![5e73b31d882682f057e25349a5049a96](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/zh_CN/5e73b31d882682f057e25349a5049a96.png) |  √   |
|     Copy      |                    null                    |                             null                             |  ×   |
|   Copy Drag   |                  拖拽拷贝                  | ![7dcad94fa0f159c669ab6a7de8fc1a41](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/7dcad94fa0f159c669ab6a7de8fc1a41.png) |  ×   |
| Counting系列  |                    null                    |                             null                             |  ×   |
|   Crosshair   |               图片的矩形区域               | ![56bf017e5b6d1f6ca6dfc0813ff2de7b](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/zh_CN/56bf017e5b6d1f6ca6dfc0813ff2de7b.png) |  ×   |
|  Crosshair 2  |                截屏选择十字                | ![b5c1bfedcd3c6353a3f0ea987a760d43](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/zh_CN/b5c1bfedcd3c6353a3f0ea987a760d43.png) |  ×   |
|    Ctx系列    |                    null                    |                             null                             |  ×   |
|     Empty     |                    null                    |                             null                             |  ×   |
|   Forbidden   |                   不允许                   | ![de23c102ecd137236bed379a4b09b691](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/en_AU/de23c102ecd137236bed379a4b09b691.png) |  √   |
|     Help      | (好像基本见不到了，在抓图可以看到他的身影) |                              ?                               |  ×   |
|     IBeam     |                  插入文本                  | ![e607c4162a8fb2650e48e674aaade097](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/e607c4162a8fb2650e48e674aaade097.png) |  √   |
|   IBeam H.    |                    null                    |                             null                             |  ×   |
|   IBeamXOR    |                    null                    |                             null                             |  ×   |
|     Move      |                    null                    |                             null                             |  ×   |
|     Link      |                    null                    |                             null                             |  ×   |
|     Open      |         摊开的手(详见mac官方文档)          | ![fe220c362c555165475f83b085ed0b94](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/en_AU/fe220c362c555165475f83b085ed0b94.png) |  √   |
|   Pointing    |                  点击链接                  | ![ef7e7351ec881269ade953411d7b04e1](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/ef7e7351ec881269ade953411d7b04e1.png) |  √   |
|     Poof      |                    null                    |                             null                             |  ×   |
|  Resize系列   |    (应该是与window系列合并成移动系列了)    |                             null                             |  ×   |
|     Wait      |                  等待光标                  | ![b7036c503ca5c75538eb42b1fda8f60b](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/b7036c503ca5c75538eb42b1fda8f60b.png) |  √   |
|  Window系列   |               各个方向的移动               | ![0eb5b604ca578d6cb8d651e5a5073682](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/0eb5b604ca578d6cb8d651e5a5073682.png) |  √   |
|    Zoom In    |                    放大                    |                             null                             |  ×   |
|   Zoom Out    |                    缩小                    |                             null                             |  ×   |

| mousecape命名 | 解释                      |                             展示                             | 可用 |
| ------------- | ------------------------- | :----------------------------------------------------------: | :--: |
| Arrow         | 默认箭头                  | ![a0d5e859e5f2b01dbbf81dfc38a3a92f](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/a0d5e859e5f2b01dbbf81dfc38a3a92f.png) |  √   |
| Camera2       | 捕捉窗口或菜单            | ![a1d807299b5280d18764e80ef9803960](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/en_AU/a1d807299b5280d18764e80ef9803960.png) |  √   |
| Closed        | 并拢的手(详见mac官方文档) | ![5e73b31d882682f057e25349a5049a96](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/zh_CN/5e73b31d882682f057e25349a5049a96.png) |  √   |
| Forbidden     | 不允许                    | ![de23c102ecd137236bed379a4b09b691](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/en_AU/de23c102ecd137236bed379a4b09b691.png) |  √   |
| IBeam         | 插入文本                  | ![e607c4162a8fb2650e48e674aaade097](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/e607c4162a8fb2650e48e674aaade097.png) |  √   |
| Open          | 摊开的手(详见mac官方文档) | ![fe220c362c555165475f83b085ed0b94](https://help.apple.com/assets/5E1917EE680CE2662245B09C/5E1917F1680CE2662245B0A3/en_AU/fe220c362c555165475f83b085ed0b94.png) |  √   |
| Pointing      | 点击链接                  | ![ef7e7351ec881269ade953411d7b04e1](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/ef7e7351ec881269ade953411d7b04e1.png) |  √   |
| Wait          | 等待光标                  | ![b7036c503ca5c75538eb42b1fda8f60b](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/b7036c503ca5c75538eb42b1fda8f60b.png) |  √   |
| Window系列    | 各个方向的移动            | ![0eb5b604ca578d6cb8d651e5a5073682](https://help.apple.com/assets/5AA195BD094622847B7F3DA3/5AA195BE094622847B7F3DAA/zh_CN/0eb5b604ca578d6cb8d651e5a5073682.png) |  √   |

> PS.可以去看一下知乎上的[这篇文章](https://zhuanlan.zhihu.com/p/36726332)。

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>