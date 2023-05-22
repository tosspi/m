---
title: "Rime鼠须管输入法续"
date: 2023-05-17T13:32:12+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
![rime](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/rime.png)

<font size=4 color=#ffa07a>今天在找“哔哔了啥”的解决方案，发现[木木大佬](https://immmmm.com/) 的博客内关于Rime的文章。</font><br>
![517-1](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/517-1.png) <br>
<font size=4 color=#ffa07a>原先用的是[三十年河东的朙月拼音](https://ssnhd.com/2022/01/06/rime/) Github: [https://github.com/ssnhd/rime](https://github.com/ssnhd/rime) 。</font><br>
![517-2](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/517-2.png)
<br>
<font size=4 color=#ffa07a>通过木木大佬的文章，发现还有个[雾凇拼音](https://dvel.me/posts/rime-ice/) Github: [https://github.com/iDvel/rime-ice](https://github.com/iDvel/rime-ice) ,感觉也不错，主要是U模式拆字，决定开搞。</font>


<br> 

![517-3](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/517-3.png)

<br>


<font size=4 color=#ffa07a>搞完以后用着真舒服，词库跟 朙月拼音 整合了一下。</font>

<font size=4 color=#ffa07a>更换了微信皮肤</font>

![517-4](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/517-4.png)

<font size=4 color=#ffa07a>有了u开头两分拼字，弥补了不知道拼音时的尴尬</font>
![517-5](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/517-5.png)

<font size=4 color=#ffa07a>有了v开头，symbols字符，可以自定义</font>

![517-6](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/517-6.png)

<font size=4 color=#ffa07a>安装了[霞鹜文楷](https://github.com/lxgw/LxgwWenKai) , 并作为鼠须管的字体使用。</font>

![517-8](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/517-8.png)

<font size=4 color=#ffa07a>以下是方案设计</font>
***
```

.
├── default.yaml   # 一些全局设置

├── rime_ice.schema.yaml  # 全拼方案
├── double_pinyin*.yaml   # 双拼方案
├── rime_ice.dict.yaml    # 挂载词库
├── cn_dicts/             # 词库目录

├── melt_eng.schema.yaml  # 英文方案，作为次翻译器挂载到拼音方案
├── melt_eng.dict.yaml    # 挂载词库
├── en_dicts/             # 词库目录

├── liangfen.schema.yaml  # 两分方案，作为反查挂载到拼音方案
├── liangfen.dict.yaml    # 两分词库

├── squirrel.yaml  # 鼠须管的皮肤、默认中英设置

├── symbols_v.yaml            # 全拼 v 模式
├── symbols_caps_v.yaml       # 双拼 V 模式
├── custom_phrase.txt         # 自定义短语
├── opencc/                   # 词语映射，Emoji
├── rime.lua                  # 引入 Lua 脚本
├── lua/                      # 各个 Lua 脚本
└── zh-hans-t-essay-bgw.gram  # 八股文
```
***


![rime-4](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/rime-4.png)