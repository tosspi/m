---
title: "macOS连接Win共享打印机"
date: 2023-06-19T08:53:25+08:00
draft: true
---

![23061900](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23061900.png)

&emsp;&emsp;macOS链接Win共享打印机试过好几种方法都无法正常打印，可以正常链接成功，就是无法打印，也不知道哪的原因，折腾了半天，终于通过LPD/LPR的方式添加成功，可以正常打印。
<br>

![23061901](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23061901.png)


![23061902](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23061902.png)

&emsp;&emsp;点击`添加打印机、扫描仪或传真机...`然后选择高级，如果没有可以在上方空白处右键点击`自定工具栏...`然后把高级添加上。
<br>

![23061903](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23061903.png)

&emsp;&emsp;选择`LPD/LPR主机或打印机`。
<br>

![23061904](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23061904.png)

&emsp;&emsp;URL里边填写Win主机的IP地址和共享打印机的名称，这里要注意一下，共享打印机名称中如果有空格，需要使用`%20`来代替空格。
<br>

&emsp;&emsp;`名称：`可以随便填写，也可以保持默认；

&emsp;&emsp;`位置：`不用管；

&emsp;&emsp;`使用：`这里需要选择对应的驱动，如果没有需要先安装驱动。

&emsp;&emsp;最后点击添加,就OK啦，快打印一张试试吧。
![23061905](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/23061905.png)

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>