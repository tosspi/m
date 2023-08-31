---
title: "记录MacOS不休眠"
date: 2023-08-31T16:32:35+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---

前两天突然发现MacOS无法休眠了，排查了好多原因，包括近期安装的软件也卸载了，还是无法解决问题，最终通过`pmset -g`查看当前的睡眠计划找到了问题所在。

![141693450044_.pic](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/141693450044_.pic.jpg)

是因为`sharingd`而导致无法睡眠。

通过搜索，发现需要重置SMC，那就很简单了：

1.连接电源；

2.关机，同时按下`Shift`+`Control`+`Option`+`开机键`，1-2秒松手。

这样就重置成功了，开机发现一切正常了。

感觉以后还是会需要重置SMC。



>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>