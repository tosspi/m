---
title: "解决Win11连接共享打印机报错"
date: 2024-10-17T21:24:54+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---

![2021072918112914](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2021072918112914.8vmwnvc01i.jpg)

&emsp;&emsp;自从更新Win10、Win11办公室共享打印机一直连接不上，折腾好久了一直也不行，各种方法都是过了，抛弃macOS拥抱Windows了，今天得空再折腾改一下，没想到解决了。

&emsp;&emsp;按照网上的说法，最多的是注册表：

&emsp;&emsp;新建记事本文档，输入如下内容：

```
Windows Registry Editor Version 5.00

［HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Print］

“RpcAuthnLevelPrivacyEnabled”=dword:00000000

［HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\Printers\PointAndPrint］

“RestrictDriverInstallationToAdministrators”=dword:00000000
```

&emsp;&emsp;然后保存，修改文件扩展名为reg，比如1.reg，然后双击这个文件导入注册表

&emsp;&emsp;弄完还是报错。

&emsp;&emsp;还有是Win+R 输入gpedit.msc。计算机配置-管理模版-打印机-配置RPC连接设置-选择“已启用”，用于传出RPC连接的协议选择“命名管道上的RPC”，应用确认。

&emsp;&emsp;弄完还是报错。

![2410171](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410171.4919n5xv2r.jpg)

![2410172](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410172.3k8035ac2d.jpg)

&emsp;&emsp;继续折腾。

&emsp;&emsp;Win+R 输入gpedit.msc。计算机配置-管理模板-网络-Lanman工作站：启用不安全的来宾登录，配置为已启用。应用保存。

&emsp;&emsp;尝试连接，还是报错。

![2410173](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410173.5mnsr78x3r.jpg)
![2410174](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410174.4n7pe165y1.jpg)
![202410175](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/202410175.5fkkvrmro1.jpg)

&emsp;&emsp;启用Guest账户

&emsp;&emsp;右键此电脑-管理-系统工具-本地用户和组-用户-双击 Guest，账户已禁用取消勾选，应用&确认。

![2410175](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410175.8z6ilkphfs.jpg)
![2410177](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410177.9nzs5ld0g9.jpg)
![2410178](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410178.3d4s7po6mj.jpg)

&emsp;&emsp;添加一个Windows凭据

![2410179](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/2410179.7ax5odz79p.jpg)
![24101710](https://cdn.jsdelivr.net/gh/tosspi/picx-images-hosting@master/24101710.45hnpg4scu.jpg)

&emsp;&emsp;重启打印服务，尝试连接打印机居然成功了。

> ps.不知道以上步骤有没有多余的步骤，有时间用办公室其他电脑试一下. 





>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>





