---
title: "开源Rime输入法[鼠须管]的傻瓜式配置之路"
date: 2022-09-22T10:56:44+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---
![WX20220913-111109](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220913-111109.png)
## 写在开头的介绍
最近发现了一款开源输入法[Rime|中州韵输入法](https://rime.im/),是一个跨平台的输入法算法框架，基于这一框架，Rime开发者与其他开源社区的参与者在Windows、Mac OS、Linux、Android等平台上创造了不同的输入法前端实现，Windows版本叫小狼毫（Weasel），Mac OS版本叫鼠须管（Squirrel），Linux版本叫ibus-rime，Android版本叫同文（Tongwen Rime Input Method Editor）。
Rime|中州韵输入法不同于我们以往使用的百度、搜狗、讯飞等输入法，它的配置上有一定的门槛，再就是它是开源的，不用担心会联网泄漏隐私等。
网上有许多配置方案，我们完全可以拿来使用，比如我现在使用的这个--[Rime Squirrel 鼠须管配置文件（朙月拼音、小鹤双拼、自然码双拼）](https://github.com/ssnhd/rime)。
## 特点
> + 朙月拼音（默认）、小鹤双拼、自然码双拼
> + 词库不丢失，支持多平台同步
> + 百万词库（城市信息、自然科学、社会科学、工程应用、农林渔畜、医药医学、电子游戏、艺术设计、生活百科、运动休闲、人文科学、娱乐休闲）
> + Emoji
> + 动态输入时间、日期、星期
> + 速度快、开源、保护隐私、自定义强
![图片](https://camo.githubusercontent.com/27e9bbddbcd2b7e46dd8a680812f46886ee6c5ae70c7f6c186c5b410223ba80f/68747470733a2f2f692e696d6775722e636f6d2f6d4d4d365466742e706e67)
## 安装
下载[鼠须管](https://rime.im/download/)(因为我的是Macbook 所以我下载的是鼠须管，当然本文介绍的配置也是鼠须管的，小狼毫等没有设备没有研究。)安装后选择鼠须管输入法，默认的是繁体输入，通过快捷键**control + ~** 切换输入方式，例如选择【朙月拼音·简化字】简体输出。
## 配置
1、下载[配置文件](https://github.com/ssnhd/rime/archive/refs/heads/master.zip),解压后得道两个文件夹【配置文件】和【花园明朝字体】，将字体安装到字体册（Mac OS缺少的生僻字）。
2、点击菜单栏ㄓ】-【用户设定】，将【配置文件】里所有文件粘贴进去，并选择覆盖。
3、点击菜单栏【ㄓ】-【重新部署】（快捷键 Control+Option+｀），至此完成定制配置，可以愉快的使用了，剩下的就是慢慢的养词库了。
![WX20220913-112926](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220913-112926.png)
## 写在最后（鼠须管配置稍详解）
### 全局设置
全局设置文件 ***default.custom.yaml*** ，包含输入方案、候选词个数、中英文切换、快捷键。
以下为我的配置文件内容：
```
patch:
  schema_list:
    - schema: luna_pinyin_simp # 朙月拼音
    - schema: double_pinyin_flypy # 小鹤双拼
    - schema: double_pinyin # 自然码双拼
    - schema: numbers # 大写数字

  menu/page_size: 9 # 候选词个数

  # 若 caps 切换大小写无效, 打开 Mac 系统偏好设置 > 键盘 > 输入法 > 取消勾选[使用大写锁定键切换“美国”输入模式]
  ascii_composer/good_old_caps_lock: true # 若为 true， Caps 只切换大小写
  ascii_composer/switch_key:
    Caps_Lock: commit_code # Caps 键
    Shift_L: commit_code # 左 Shift，切换中英文
    Shift_R: commit_code # 右 Shift，切换中英文
    Control_L: noop # 左 Control，屏蔽该切换键
    Control_R: noop # 右 Control，屏蔽该切换键

  key_binder/bindings: # 若开启, 去掉前面#
    # 翻页
    #- { when: has_menu, accept: Tab, send: Page_Down }            # "tab" 键翻页, 和 "tab" 键分词只能二选一
    - { when: composing, accept: Tab, send: Shift+Right } # "tab" 键分词
    - { when: paging, accept: minus, send: Page_Up } # "-" 上一页
    - { when: has_menu, accept: equal, send: Page_Down } # "=" 下一页
    - { when: paging, accept: comma, send: Page_Up } # "," 上一页
    - { when: has_menu, accept: period, send: Page_Down } # "." 下一页
    - { when: paging, accept: bracketleft, send: Page_Up } # "[" 上一页
    - { when: has_menu, accept: bracketright, send: Page_Down } # "]" 下一页
    # 快捷键
    #- { when: has_menu, accept: semicolon, send: 2 }              # ":" (分号)选择第 2 个候选词
    #- { when: has_menu, accept: apostrophe, send: 3 }             # "'" (引号)选择第 3 个候选词
    #- { when: composing, accept: Shift+Tab, send: Shift+Left }    # "Shift+Tab" 键向左选拼音分词
    #- { when: composing, accept: Control+a, send: Home }          # "Control+a" 光标移至首
    #- { when: composing, accept: Control+e, send: End }           # "Control+e" 光标移至尾
    #- { when: composing, accept: Control+g, send: Escape }        # "Control+g" 清码
    #- { when: composing, accept: Return, send: Escape }           # "Return" 回车清码
    #- { when: always, accept: Control+Shift+1, select: .next }             # 切换输入方案
    #- { when: always, accept: Control+Shift+2, toggle: ascii_mode }        # 中/英文切换
    #- { when: always, accept: Control+Shift+3, toggle: full_shape }        # 全角/半角切换
    - { when: always, accept: Control+Shift+4, toggle: simplification } # 繁简体切换
    #- { when: always, accept: Control+Shift+5, toggle: extended_charset }  # 通用/增广切换（显示生僻字）
    #- { when: composing, accept: Control+b, send: Left }           # "Control+b" 移动光标
    #- { when: composing, accept: Control+f, send: Right }          # "Control+f" 向右选择候选词
    #- { when: composing, accept: Control+h, send: BackSpace }      # "Control+h" 删除输入码
```
### 词库格式
新建文件命名格式为 ***<词库名>.dict.yaml***
比如导入百度下载的词库 ***luna_pinyin.baidu.dict.yaml***
![WX20220913-163307](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220913-163307.png)
### 词库外挂
打开 ***luna_pinyin.extended.dict.yaml*** ，将词库名添加。
如下：
```
# Rime dictionary
# encoding: utf-8
# Luna Pinyin Extended Dictionary(Basic)  - 明月拼音扩充词库（基本）

---
name: luna_pinyin.extended      # 词库名
version: "2021.02.07"
sort: by_weight                 # by_weight（按词频高低排序）或 original（保持原码表中的顺序）
use_preset_vocabulary: true     # true 或 false，选择是否导入预设词汇表【八股文】

import_tables:
  - luna_pinyin
  - luna_pinyin.sogou
  - luna_pinyin.baidubeifen
  - luna_pinyin.huagong
  - luna_pinyin.shuili
  - luna_pinyin.dianshang
  - luna_pinyin.baidu

```
### 词库载入及模式转换
打开 ***luna_pinyin_simp.custom.yaml***
switches 列了：中文西文、全角半角、Emoji、简繁体、字节编码。
载入中英文词库，还可以修改英文候选词位置、Emoji 显示注释等。
以下为我的配置：
```
patch:
  switches:
    - name: ascii_mode # 0 中文，1 英文
      reset: 0
      states: ["中文", "西文"]
    - name: full_shape # 全角/半角符号开关
      states: ["半角", "全角"]
    - name: show_emoji # Emoji 开关
      reset: 1
      states: ["🈚️️\uFE0E", "🈶️️\uFE0F"]
    - name: zh_simp # (※1) 繁简转换
      reset: 1
      states: ["漢字", "汉字"]
    - options: ["utf8", "gbk", "gb2312"] # (※2)字符集选单
      reset: 0 # 默认 UTF8
      states:
        - UTF-8
        - GBK
        - GB2312

  simplifier:
    option_name: zh_simp

  # 启用罕见字過濾
  engine/filters:
    - simplifier
    - simplifier@emoji_conversion
    - uniquifier
    - charset_filter@gbk # (※3) GBK 过滤
    - single_char_filter

  emoji_conversion:
    opencc_config: emoji.json
    option_name: show_emoji
    tags: abc
    #tips: all    # Emoji 显示注释

  # 改写拼写运算，含英文的词汇（luna_pinyin.cn_en.dict.yaml）不影响简拼
  "speller/algebra/@before 0": xform/^([b-df-hj-np-tv-z])$/$1_/

  # 载入朙月拼音扩充词库
  "translator/dictionary": luna_pinyin.extended

  # 加载easy_en依赖
  "schema/dependencies/@1": easy_en
  # 载入翻译英文的码表翻译器，取名为 english
  "engine/translators/@4": table_translator@english
  # english翻译器的设定项
  english:
    dictionary: easy_en
    spelling_hints: 9
    enable_completion: false # 是否启用英文输入联想补全
    enable_sentence: false # 混输时不出现带有图案的英文
    initial_quality: -0.5 # 英文候选词的位置, 数值越大越靠前。

  # 快捷表情和符号
  punctuator:
    import_preset: symbols
    symbols:
      "/fs": [½, ‰, ¼, ⅓, ⅔, ¾, ⅒]
      "/xh": [＊, ×, ✱, ★, ☆, ✩, ✧, ❋, ❊, ❉, ❈, ❅, ✿, ✲]
      "/dq": [🌍, 🌎, 🌏, 🌐, 🌑, 🌒, 🌓, 🌔, 🌕, 🌖, 🌗, 🌘]
      "/sg": [🍇, 🍉, 🍌, 🍍, 🍎, 🍏, 🍑, 🍒, 🍓, 🍗, 🍦, 🎂, 🍺, 🍻]
      "/dw": [🙈, 🐵, 🐈, 🐷, 🐨, 🐼, 🐾, 🐔, 🐬, 🐠, 🦋]
      "/bq": [😀, 😁, 😂, 😃, 😄, 😅, 😆, 😉, 😊, 😋, 😎, 😍, 😘, 😗]
      "/ss": [💪, 👈, 👉, 👆, 👇, ✋, 👌, 👍, 👎, ✊, 👊, 👋, 👏, 👐]
      "/sx": [＝, ＜, ≤, ＞, ≥, ≈, ~, ℃, °]
    half_shape:
      "#": "#"
      "*": "*"
      "`": "`"
      "~": "~"
      "@": "@"
      "=": "="
      '\': "、"
      "%": "%"
      "$": ["¥", "$"]
      "|": ["|", "｜", "·"]
      "/": ["/", "÷"]
      "'": { pair: ["「", "」"] }
      "[": "【"
      "]": "】"
      "<": "《"
      ">": "》"

  recognizer/patterns/punct: "^/([a-z]+|[0-9]0?)$"

  # 模糊拼音
  "speller/algebra":
    - erase/^xx$/ # 第一行保留

    # 模糊音定義
    # 需要哪組就刪去行首的 # 號，單雙向任選
    #- derive/^([zcs])h/$1/             # zh, ch, sh => z, c, s
    #- derive/^([zcs])([^h])/$1h$2/     # z, c, s => zh, ch, sh

    #- derive/^n/l/                     # n => l
    #- derive/^l/n/                     # l => n

    # 這兩組一般是單向的
    #- derive/^r/l/                     # r => l

    #- derive/^ren/yin/                 # ren => yin, reng => ying
    #- derive/^r/y/                     # r => y

    # 下面 hu <=> f 這組寫法複雜一些，分情況討論
    #- derive/^hu$/fu/                  # hu => fu
    #- derive/^hong$/feng/              # hong => feng
    #- derive/^hu([in])$/fe$1/          # hui => fei, hun => fen
    #- derive/^hu([ao])/f$1/            # hua => fa, ...

    #- derive/^fu$/hu/                  # fu => hu
    #- derive/^feng$/hong/              # feng => hong
    #- derive/^fe([in])$/hu$1/          # fei => hui, fen => hun
    #- derive/^f([ao])/hu$1/            # fa => hua, ...

    # 韻母部份
    #- derive/^([bpmf])eng$/$1ong/      # meng = mong, ...
    #- derive/([ei])n$/$1ng/            # en => eng, in => ing
    #- derive/([ei])ng$/$1n/            # eng => en, ing => in

    # 樣例足夠了，其他請自己總結……

    # 反模糊音？
    # 誰說方言沒有普通話精確、有模糊音，就能有反模糊音。
    # 示例爲分尖團的中原官話：
    #- derive/^ji$/zii/   # 在設計者安排下鳩佔鵲巢，尖音i只好雙寫了
    #- derive/^qi$/cii/
    #- derive/^xi$/sii/
    #- derive/^ji/zi/
    #- derive/^qi/ci/
    #- derive/^xi/si/
    #- derive/^ju/zv/
    #- derive/^qu/cv/
    #- derive/^xu/sv/
    # 韻母部份，只能從大面上覆蓋
    #- derive/^([bpm])o$/$1eh/          # bo => beh, ...
    #- derive/(^|[dtnlgkhzcs]h?)e$/$1eh/  # ge => geh, se => sheh, ...
    #- derive/^([gkh])uo$/$1ue/         # guo => gue, ...
    #- derive/^([gkh])e$/$1uo/          # he => huo, ...
    #- derive/([uv])e$/$1o/             # jue => juo, lve => lvo, ...
    #- derive/^fei$/fi/                 # fei => fi
    #- derive/^wei$/vi/                 # wei => vi
    #- derive/^([nl])ei$/$1ui/          # nei => nui, lei => lui
    #- derive/^([nlzcs])un$/$1vn/       # lun => lvn, zun => zvn, ...
    #- derive/^([nlzcs])ong$/$1iong/    # long => liong, song => siong, ...
    # 這個辦法雖從拼寫上做出了區分，然而受詞典制約，候選字仍是混的。
    # 只有真正的方音輸入方案纔能做到！但「反模糊音」這個玩法快速而有效！

    # 模糊音定義先於簡拼定義，方可令簡拼支持以上模糊音
    - abbrev/^([a-z]).+$/$1/ # 簡拼（首字母）
    - abbrev/^([zcs]h).+$/$1/ # 簡拼（zh, ch, sh）

    # 以下是一組容錯拼寫，《漢語拼音》方案以前者爲正
    - derive/^([nl])ve$/$1ue/          # nve = nue, lve = lue
    - derive/^([jqxy])u/$1v/           # ju = jv,
    - derive/un$/uen/                  # gun = guen,
    - derive/ui$/uei/                  # gui = guei,
    - derive/iu$/iou/                  # jiu = jiou,

    # 自動糾正一些常見的按鍵錯誤
    - derive/([aeiou])ng$/$1gn/        # dagn => dang
    - derive/([dtngkhrzcs])o(u|ng)$/$1o/  # zho => zhong|zhou
    - derive/ong$/on/                  # zhonguo => zhong guo
    - derive/ao$/oa/                   # hoa => hao
    - derive/([iu])a(o|ng?)$/a$1$2/    # tain => tian

  # 分尖團後 v => ü 的改寫條件也要相應地擴充：
  #'translator/preedit_format':
  #  - "xform/([nljqxyzcs])v/$1ü/"

  # librime-lua 输入动态时间和日期
  "engine/translators/@6": lua_translator@date_translator
```
### 词库转换
打开 [搜狗官网](https://pinyin.sogou.com/dict/cate/index/167?rf=dictindex&pos=dict_rcmd) 下载词库，格式为 .scel 文件
![WX20220913-164341](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220913-164341.png)
下载[深蓝词库转换工具]（）（PS.需要使用Windows，为了转换一个词库操碎了心）
剩下的转换就很简单了，不放图了，转换的时候没有放图。
转换过程中转出项记得选择**Rime中州韵**。
转换完成后是 ***.txt*** 格式的，需要改为 ***yaml***文件。直接重命名既可，比如我百度输入法备份的词库重命名为 ***luna_pinyin.baidubeifen.dict.yaml***
记得开头要加上以下代码：
```
#  此处可以写一个备注，可以将包含哪些词库写在此处，方便日后查看是否有重复。
    
---
name: luna_pinyin.baidubeifen #词库名称（自定义）
version: "2022.08.29"#日期
sort: by_weight
use_preset_vocabulary: true
...

```
* ⚠️注意最后 *** ... *** 下面要空一行 
![WX20220913-170127](https://cdn.jsdelivr.net/gh/imum-me/img@main/uPic/WX20220913-170127.png)

>&emsp;&emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>