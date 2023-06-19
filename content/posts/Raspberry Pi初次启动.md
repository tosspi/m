---
title: "RaspberryPi初次启动"
date: 2021-11-06T10:56:44+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---

&emsp;&emsp;2023.5.22迁移博客文章看到更新

&emsp;&emsp;现在树莓派在丈母娘家当表用，DIY了一个显示器，安装了类似Fliqlo的屏幕保护程序，在电视柜上充当一个钟表！！！！！

&emsp;&emsp;暴殄天物！！！！！！！

# Raspberry Pi初次启动

![Raspberry Pi](https://gitee.com/TossPi/blogimg/raw/master/img/树莓派.png)

&emsp;&emsp;生命不息，折腾不止

------

## 一、链接树莓派软件

&emsp;&emsp;putty、Xshell、VNV Viewer远程桌面、VSCode

&emsp;&emsp;Mac OS终端：ssh pi@192.168.x.x

![LED亮灯状态](https://gitee.com/TossPi/blogimg/raw/master/img/60A5142A-2E66-442A-A78A-A4A7479FD2B9.png)

### VSCode

&emsp;&emsp;这里说一下VSCode，真的太好用了

![VSCode](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-171229.png)

&emsp;&emsp;在线版[VSCode](https://vscode.dev/)

&emsp;&emsp;我使用的是MAC版的，下载地址[Visual Studio Code](https://code.visualstudio.com/)

#### 1、设置中文

&emsp;&emsp;在拓展里搜索Chinese

&emsp;&emsp;然后安装重启

![VSCode设置中文](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/8981636209087_.pic_hd.jpg)

#### 2、安装Remote SSH

&emsp;&emsp;在拓展里搜索Remote SSH安装

![安装 Remote SSH](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-223928.png)

#### 4、添加树莓派

![添加树莓派链接](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-224521.png)

&emsp;&emsp;然后输入ssh 用户名@ip -A

&emsp;&emsp;后期也可以更改，我这里是远程链接的

![更改SSH](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-224703.png)

![添加树莓派2](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-224736.png)

&emsp;&emsp;Host:显示的名称

&emsp;&emsp;HOSTName:树莓派的IP

&emsp;&emsp;User:用户名

&emsp;&emsp;Port:端口号

#### 5、链接树莓派管理文件及打开终端

![链接树莓派管理文件](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-225350.png)

&emsp;&emsp;输入密码

![输入密码](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-225422.png)

&emsp;&emsp;点击上面的终端

![链接树莓派打开终端](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-225600.png)

&emsp;&emsp;接下来愉快的使用树莓派吧

![愉快的使用树莓派把](https://cdn.jsdelivr.net/gh/tosspi/img@main//img/WX20211106-225705.png)

## 二、初始账号密码

&emsp;&emsp;初始账号密码：pi  raspberry

&emsp;&emsp;链接成功后输入passwd可修改初始密码

## 三、安装中文支持

```
sudo apt-get install ttf-wqy-zenhei #安装文泉驿字体
sudo fc-cache #刷新字库缓存
sudo dpkg-reconfigure locales #配置字体
sudo raspi-config #设置
sudo apt-get install scim-pinyin #安装中文拼音输入法
设置显示中文。
终端下执行命令：sudo raspi-config
选择：4 Localisation Options  -->  I1 Change Locale
操作提示：按空格键在前面打勾或去掉勾（星号=勾），PageUp PageDown快速翻页，Tab键跳到OK按钮上
去掉en_GB.UTF-8 UTF-8，
勾上：“en_US.UTF-8 UTF-8”、“zh_CN.UTF-8 UTF-8”、“zh_CN.GBK GBK”
下一屏幕默认语言选zh_CN.UTF-8。
```

&emsp;&emsp;在众多选项中找到**en_GB.UTF-8 UTF-8，**系统默认是这个，前面有个‘*’，敲空格可以去掉这个星号，用pagedown翻页比较快，去掉之后从里面找到**”en_US.UTF-8 UTF-8“，”zh_CN.UTF-8 UTF-8“，”zh_CN.GBK GBK”**这三个选项， 用空格键在前面加上星号。

## 四、替换软件源

&emsp;&emsp;软件源在线配置工具已上线，一键生成更新命令，再也不用手打指令啦

https://tech.biko.pub/tool#/rpi-apt-sources

（~# cat /etc/debian_version 查看版本号）

&emsp;&emsp;Debian10自动执行脚本：

```
wget -qO- https://tech.biko.pub/resource/rpi-replace-apt-source-buster.sh | sudo bash
```

> https://mirrors.tuna.tsinghua.edu.cn/help/raspbian/  #清华大学开源软件镜像站

```
sudo apt-get update 更新升级连接文件
sudo apt-get dist-upgrade 更新并安装程序
sudo apt-get clean 清空系统不使用的旧文件
```

> 中国科学技术大学
>
> Raspbian http://mirrors.ustc.edu.cn/raspbian/raspbian/
>
> 
>
> 
>
> 阿里云
>
> Raspbian http://mirrors.aliyun.com/raspbian/raspbian/
>
> 
>
> 
>
> 清华大学
>
> Raspbian http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/
>
> 
>
> 
>
> 华中科技大学
>
> Raspbian http://mirrors.hustunique.com/raspbian/raspbian/
>
> Arch Linux ARM http://mirrors.hustunique.com/archlinuxarm/
>
> 
>
> 
>
> 华南农业大学（华南用户）
>
> Raspbian http://mirrors.scau.edu.cn/raspbian/
>
> 
>
> 
>
> 大连东软信息学院源（北方用户）
>
> Raspbian http://mirrors.neusoft.edu.cn/raspbian/raspbian/
>
> 
>
> 
>
> 重庆大学源（中西部用户）
>
> Raspbian http://mirrors.cqu.edu.cn/Raspbian/raspbian/
>
> 
>
> 
>
> 中山大学 已跳转至中国科学技术大学源
>
> Raspbian http://mirror.sysu.edu.cn/raspbian/raspbian/
>
> 
>
> 
>
> 新加坡国立大学
>
> Raspbian http://mirror.nus.edu.sg/raspbian/raspbian
>
> 
>
> 
>
> 牛津大学
>
> Raspbian http://mirror.ox.ac.uk/sites/archive.raspbian.org/archive/raspbian/
>
> 
>
> 
>
> 韩国KAIST大学
>
> Raspbian http://ftp.kaist.ac.kr/raspbian/raspbian/

### PS.另一种换源方式：

#### 1、**备份原始文件（可选步骤）**

```
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
sudo cp /etc/apt/sources.list.d/raspi.list /etc/apt/sources.list.d/raspi.list.bak
```

#### 2、**编辑软件源配置**

&emsp;&emsp;编辑 /etc/apt/sources.list 文件（软件源），参考如下命令：

```
sudo nano /etc/apt/sources.list
```

&emsp;&emsp;删除原文件所有内容，

&emsp;&emsp;**buster** 系统用以下内容取代：

```
deb http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib
deb-src http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib
```

&emsp;&emsp;注：网址末尾的raspbian重复两次是必须的。因为Raspbian的仓库中除了APT软件源还包含其他代码。APT软件源不在仓库的根目录，而在raspbian/子目录下。

&emsp;&emsp;**stretch** 系统用以下内容取代：

```
deb http://mirrors.sysu.edu.cn/raspbian/raspbian/ stretch main contrib non-free
deb-src http://mirrors.sysu.edu.cn/raspbian/raspbian/ stretch main contrib non-free
```

&emsp;&emsp;**jessie** 用以下内容取代：

```
deb http://mirrors.sysu.edu.cn/raspbian/raspbian/ jessie main contrib non-free
deb-src http://mirrors.sysu.edu.cn/raspbian/raspbian/ jessie main contrib non-free
```

&emsp;&emsp;**wheezy** 用以下内容取代：

```
deb http://mirrors.sysu.edu.cn/raspbian/raspbian/ wheezy main contrib non-free
deb-src http://mirrors.sysu.edu.cn/raspbian/raspbian/ wheezy main contrib non-free
```

（**buster、**stretch、**jessie、**wheezy为Debian版本号）

&emsp;&emsp;Ctrl+o 保存，之后回车确认，然后 Ctrl+x 退出。

**编辑系统源配置**

&emsp;&emsp;编辑 /etc/apt/sources.list.d/raspi.list 文件（系统更新源），参考如下命令：

```
sudo nano /etc/apt/sources.list.d/raspi.list
```

&emsp;&emsp;同样修改首行网址，修改后文件如下：

```
deb http://mirrors.tuna.tsinghua.edu.cn/raspberrypi/ buster main ui
# Uncomment line below then 'apt-get update' to enable 'apt-get source'
#deb-src http://archive.raspberrypi.org/debian/ stretch main ui
```

&emsp;&emsp;jessie、wheezy 版本的系统按照之前修改软件源的的规则修改即可，这里不再赘述。

&emsp;&emsp;Ctrl+o 保存，之后回车确认，然后 Ctrl+x 退出。

**更新**

&emsp;&emsp;配置好了可以尝试更新，用下面的命令分别更新软件源列表、软件版本和系统内核版本，完整的更新过程需要等挺久的。一般只用更新软件源列表即可。

```
#更新软件源列表
sudo apt-get update
#更新软件版本
sudo apt-get upgrade
sudo apt-get dist-upgrade
#更新系统内核
sudo rpi-update
```

&emsp;&emsp;如果需要，你可以执行以下命令将Raspbian public key加入你的 apt-get keyring :

```
wget http://archive.raspbian.org/raspbian.public.key -O - | sudo apt-key add -
```

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>