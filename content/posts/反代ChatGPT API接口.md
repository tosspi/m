---
title: "反代ChatGPT API接口"
date: 2023-06-09T10:48:58+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
![2360900](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360900.JPEG)
## <font color=#ffa07a>前言</font>
&emsp;&emsp;<font size=3 color=#255b21>今天研究[Bob翻译](https://bobtranslate.com/),使用OpenAI确实很香，但是要全局开代理，于是有了反代ChatGPT接口，实现国内免翻使用，其实很简单，通过宝塔面板实现，零代码、零部署。</font><br>
&emsp;&emsp;<font size=3 color=#255b21>条件：</font><br>
&emsp;&emsp;<font size=3 color=#255b21>海外VPS(我使用的是微软的Azure，薅了一年的免费)</font><br>
&emsp;&emsp;<font size=3 color=#255b21>以下是过程</font><br>
## <font color=#ffa07a>新建站点-绑定域名</font>
![2360901](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360901.png)

## <font color=#ffa07a>部署SSL证书</font>
![2360902](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360902.png)
## <font color=#ffa07a>添加反向代理</font>
![2360902](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360903.png)
&emsp;&emsp;<font size=3 color=#255b21>目标URL：https://api.openai.com   发送域名：api.openai.com</font><br>
&emsp;&emsp;<font size=3 color=#255b21>验证结果</font><br>
&emsp;&emsp;<font size=3 color=#255b21>分别浏览器输入https://api.openai.com与反代域名，查看是否一致。</font><br>
![2360900](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360900.JPEG)

## <font color=#ffa07a>问题</font>
&emsp;&emsp;<font size=3 color=#255b21>如果出现502 Bad Gateway问题</font><br>
![2360905](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360905.png)

&emsp;&emsp;<font size=3 color=#255b21>应该是SSL证书不匹配造成的问题，可以在反向代理配置文件中添加两行代码解决</font><br>
![2360904](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360904.png)
```
proxy_ssl_server_name on;
proxy_ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
```
&emsp;&emsp;<font size=3 color=#255b21>点击保存，然后测试一下</font><br>
![2360906](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/2360906.png)
&emsp;&emsp;<font size=3 color=#255b21>一切OK</font><br>
&emsp;&emsp;<font size=3 color=#255b21>测试下Bob翻译，Perfect.</font><br>
![QFOdeK](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/QFOdeK.png)


>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>