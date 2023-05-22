---
title: "Rime鼠须管输入法续"
date: 2023-05-17T13:32:12+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
![rime](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/rime.png)

今天在找“哔哔了啥”的解决方案，发现[木木大佬](https://immmmm.com/) 的博客内关于Rime的文章。<br>
![PastedGraphic](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/Pasted Graphic.png) <br>
原先用的是[三十年河东的朙月拼音](https://ssnhd.com/2022/01/06/rime/) Github:https://github.com/ssnhd/rime 。<br>
![PastedGraphic1](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/Pasted Graphic 1.png)
<br>
通过木木大佬的文章，发现还有个[雾凇拼音](https://dvel.me/posts/rime-ice/) Github:https://github.com/iDvel/rime-ice ,感觉也不错，主要是U模式拆字，决定开搞。


<br> 
![PastedGraphic2](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/Pasted Graphic 2.png) 
<br>


搞完以后用着真舒服，词库跟 朙月拼音 整合了一下。

更换了微信皮肤
![PastedGraphic3](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/Pasted Graphic 3.png)

有了u开头两分拼字，弥补了不知道拼音时的尴尬
![PastedGraphic4](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/Pasted Graphic 4.png)

有了v开头，symbols字符，可以自定义

![PastedGraphic5](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/Pasted Graphic 5.png)

安装了[霞鹜文楷](https://github.com/lxgw/LxgwWenKai) , 并作为鼠须管的字体使用。

![PastedGraphic6](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/Pasted Graphic 6.png)

以下是方案设计
***
'''

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
'''
***


![rime-4](https://cdn.jsdelivr.net/gh/tosspi/mumu@main/uPic/rime-4.png)