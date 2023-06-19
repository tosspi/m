---
title: "Memos部署"
date: 2023-06-02T15:48:58+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---

![UifGMN](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/UifGMN.jpg)

<br>

&emsp;&emsp;自从腾讯云开发不给薅羊毛以后，[🦖胡言乱语](https://imum.me/talk/)就一直处与停摆状态，前几天突然发现 [木木大佬](https://immmmm.com/) 的博客更新了 [Memos](https://usememos.com/) 版本的哔哔了啥，于是乎，开搞。。。。<br>
&emsp;&emsp;Memos官网：[https://usememos.com/](https://usememos.com/)<br>
&emsp;&emsp;Github:[https://github.com/usememos/memos](https://github.com/usememos/memos)<br>
&emsp;&emsp;建议使用Docker部署。<br>
## 部署以及更新
&emsp;&emsp;我借鉴了木木大佬的部署，使用` docker-compose.yml ` 部署，以下是 ` docker-compose.yml ` 的代码：<br>

```
version: "3.0"
services:
  memos:
    image: neosmemo/memos:latest
    container_name: memos
    volumes:
      - ${PWD}/.memos/:/var/opt/memos
    ports:
      - 5230:5230

```
&emsp;&emsp;打开宝塔面板新建 ` docker-compose.yml ` 文件，丢入代码。<br>
![XJJdp6](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/XJJdp6.png)
![JCMThN](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/JCMThN.png)
<br>
&emsp;&emsp;打开终端输入代码：<br>
```
docker-compose up -d
```
&emsp;&emsp;搞定了。<br>

&emsp;&emsp;后期版本更新输入代码：<br>

```
docker-compose pull && docker-compose up -d --force-recreate
```
<br>
&emsp;&emsp;也可以按照官方的教程更新，但是更新前要先去Docker管理界面删除镜像，比较麻烦。<br>
PS.要不定时备份一下网址目录下的 " .memos " 文件夹，所有的数据都在里边。
<br>
&emsp;&emsp;还要设置一下反向代理，实现https://xxx.com 打开，要不然需要添加端口号比如：https://xxx.com:5230 才能访问。<br>

![SSP0o0](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/SSP0o0.png)

&emsp;&emsp;后续一些客户端设置可能需要填写OpenAPI:<br>

![B3HFh8](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/B3HFh8.png)

&emsp;&emsp;一些客户端：<br>
&emsp;&emsp;IOS:[https://apps.apple.com/app/id1643902185](https://apps.apple.com/app/id1643902185)<br>
&emsp;&emsp;MAC OS:[https://github.com/lmm214/Pake](https://github.com/lmm214/Pake)。MAC OS和Windows客户端可以用Pake自己打包。可以按照此教程进行打包：[Pake在线编译（普通用户）](https://github.com/tw93/Pake/wiki/Online-Compilation-(used-by-ordinary-users))<br>
![NkNbU4](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/NkNbU4.jpg)
![q2Zqie](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/q2Zqie.jpg)
![wpW7C2](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/wpW7C2.jpg)
![P7dDu9](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/P7dDu9.jpg)
&emsp;&emsp;浏览器扩展：[https://chrome.google.com/webstore/detail/memos-bber/cbhjebjfccgchgbmfbobjmebjjckgofe/](https://chrome.google.com/webstore/detail/memos-bber/cbhjebjfccgchgbmfbobjmebjjckgofe/)<br>
&emsp;&emsp;IOS捷径：[https://github.com/usememos/memos/discussions/52](https://github.com/usememos/memos/discussions/52)<br>

## 美化
![f1dvCx](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/f1dvCx.png)

### 调用Bing每日背景

```
html{background-image:url('https://bing.immmmm.com/img/bing?region=zh-CN&type=image');width:100%;height:100vh;background-position:center;background-size:cover;background-attachment:fixed;}
.w-full.bg-zinc-100,.bg-white,.hover\:bg-white:hover,.dark .dark\:bg-zinc-700,.dark .dark\:hover\:bg-zinc-700:hover,.memo-wrapper,.bg-gray-200,.dark .memo-wrapper,.memo-editor-container{--tw-bg-opacity:0.66 !important;}
.dark header.dark\:bg-zinc-800,aside.dark\:bg-zinc-800,.bg-gray-100,.dark html,.dark body{--tw-bg-opacity:0 !important;}
.memo-editor-container>.memo-editor{background-color: transparent !important;}
```
<br>
&emsp;&emsp;加送界面细节微调：<br>

```
.status-text{font-size:10px !important;border:none;color:rgb(156,163,175) !important;}
.tag-span,.dark .tag-span{border: 1px solid;border-radius:6px;padding:0px 6px;color:rgb(22,163,74) !important;font-size:12px !important;-webkit-transform: scale(calc(10 / 12));transform-origin: left center;}
.memo-content-text .link{color:rgb(22,163,74) !important;margin-right:-6px;}
header .bg-blue-600{display:none !important;}
.text-lg {font-size: 1rem !important;}
.header-wrapper,.sidebar-wrapper{width: 11rem !important;}
.filter-query-container{padding-bottom:0.5rem;}
```
<br>

### 加载“霞鹜文楷”在线字体

```
body{font-family: "LXGW WenKai Screen", sans-serif !important;}
```
<br>

```
function changeFont() { 
  const link = document.createElement("link");
  link.rel = "stylesheet";
  link.type = "text/css";
  link.href = "https://cdn.staticfile.org/lxgw-wenkai-screen-webfont/1.6.0/lxgwwenkaiscreen.css";
  document.head.append(link);
};
changeFont()
```
<br>

### 设置Faviocn图标为emoji

```
function changeFavicon() { 
    var link = document.head.querySelector("link[rel='icon']");
    link.href = "data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text x=%2250%%22 y=%2250%%22 style=%22dominant-baseline:central;text-anchor:middle;font-size:90px;%22>🦖</text></svg>";
};
setTimeout(function() { changeFavicon()}, 500)

```
<br>

### 随机Memos 回顾

```
function randomMemo(){
  var bbUrl1 = window.location.origin+"/api/user/me";
  fetch(bbUrl1).then(res1 => res1.json()).then( resdata1 =>{
    var creatorId = resdata1.data.id
    var bbUrl2 = window.location.origin+"/api/memo/amount?userId="+creatorId;
    fetch(bbUrl2).then(res2 => res2.json()).then( resdata2 =>{
        let randomNum = Math.floor(Math.random() * ( resdata2.data + 2))
        var bbUrl3 = window.location.origin+"/api/memo?rowStatus=NORMAL&limit=1&offset="+randomNum;
        fetch(bbUrl3).then(res3 => res3.json()).then( resdata3 =>{
          window.location.href =  window.location.origin+"/m/"+resdata3.data[0].id;
        })
    })
  })
}
setTimeout(function() { 
    document.querySelector("button.btn.action-btn").insertAdjacentHTML('afterend', '<button onclick="randomMemo()" class="btn action-btn"><span class="icon">⛳️</span> 随机</button>');
}, 1500)

```
<br>

## 接入Hugo

&emsp;&emsp;新建哔哔页面，然后丢入以下代码即可：

```
<div id="bber"></div>
<script src="https://fastly.jsdelivr.net/npm/marked/marked.min.js"></script>
<script src="https://fastly.jsdelivr.net/gh/Tokinx/ViewImage/view-image.min.js"></script>
<script src="https://fastly.jsdelivr.net/gh/Tokinx/Lately/lately.min.js"></script>
<script type="text/javascript">
  var bbMemos = {
    memos : 'https://me.edui.fun/',//修改为自己部署 Memos 的网址，末尾有 / 斜杠
    limit : '',//默认每次显示 10条
    creatorId:'1' ,//早期默认为 101 用户，新安装是 1； https://demo.usememos.com/u/101
    domId: '',//默认为 <div id="bber"></div>
  }
</script>
<script src="https://immmmm.com/bb-lmm-mk.js"></script>

```

&emsp;&emsp;PS.注意查看自己的CeatorId是几对应修改一下。<br>
![vLUrVT](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/vLUrVT.png)


&emsp;&emsp;<font size=10 color=#ffa07a>END</font>

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>