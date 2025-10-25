---
title: "Hello,Blinko"
date: 2025-10-25T22:36:39+08:00
draft: false
tags: ["折腾"]
adjacentPost: true
readingBar: true
---

![home.png](https://cdn.jsdelivr.net/gh/tosspi/picgocore@main/marktext/home.png)

&emsp;&emsp;<font size=5 color=#ffa07a>发</font>现一个很不错的开源项目-[Blinko](https://github.com/blinkospace/blinko) :是一个AI驱动的卡片笔记项目，专为那些想要快速捕捉和组织灵感的人设计。它允许用户在灵感闪现的瞬间无缝记录想法，确保不错过任何创意火花。<br>

在线演示（用户名：blinko，密码：blinko）<br>

https://demo.blinko.space/ <br>

# 开搞

考虑到已经搭了一个飞牛NAS，所以第一次部署在了飞牛NAS上，但没有考虑到飞牛NAS没有公网，所以在阿里云的服务器又部署了一个。<br>

Docker Compose（官方模板）<br>

```
services:
  blinko-website:
    image: blinkospace/blinko:latest
    container_name: blinko-website
    environment:
      NODE_ENV: production
      NEXTAUTH_URL: http://localhost:1111
      NEXT_PUBLIC_BASE_URL: http://localhost:1111
      NEXTAUTH_SECRET: my_ultra_secure_nextauth_secret
      DATABASE_URL: postgresql://postgres:mysecretpassword@postgres:5432/postgres
    volumes:
      - ./blinko:/app/.blinko
    depends_on:
      postgres:
        condition: service_healthy
    restart: always
    ports:
      - 1111:1111
    healthcheck:
      test: ["CMD", "wget", "--spider", "http://blinko-website:1111/"]
      interval: 30s 
      timeout: 10s  
      retries: 5
      start_period: 30s

  postgres:
    image: postgres:14
    container_name: blinko-postgres
    restart: always
    ports:
      - 5432:5432
    environment:
      POSTGRES_DB: postgres
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: mysecretpassword
    volumes:
      - ./db:/var/lib/postgresql/data
    healthcheck:
      test:
        ["CMD", "pg_isready", "-U", "postgres", "-d", "postgres"]
      interval: 5s
      timeout: 10s
      retries: 5
```

在飞牛的论坛上还发现了一个简洁的版本<br>

Docker Compose（简洁版）<br>

```
services:
  blinko-website:
    image: blinkospace/blinko:latest
    container_name: blinko-website
    ports:
      - 1111:1111
    environment:
      NODE_ENV: production
      NEXTAUTH_URL: http://localhost:1111
      NEXT_PUBLIC_BASE_URL: http://localhost:1111
      NEXTAUTH_SECRET: my_ultra_secure_nextauth_secret
      DATABASE_URL: postgresql://postgres:mysecretpassword@postgres:5432/postgres
    volumes:
      - ./blinko:/app/.blinko
    restart: always

  postgres:
    image: postgres:14
    container_name: blinko-postgres
    environment:
      POSTGRES_DB: postgres
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: mysecretpassword
    volumes:
      - ./db:/var/lib/postgresql/data
    restart: always
```

参数说明（更多参数建议去看文档）<br>

> :::NODE_ENV（环境变量）：设定运行环境
> 
> NEXTAUTH_URL（环境变量）：应用认证基础 URL，用于生成回调链接等
> 
> NEXT_PUBLIC_BASE_URL（环境变量）：应用全局基础 URL，用于构建各种链接和请求地址
> 
> NEXTAUTH_SECRET（环境变量）：用于加密会话数据的密钥，替换为随机字符串
> 
> DATABASE_URL（环境变量）：数据库连接地址
> 
> POSTGRES_DB（环境变量）：创建的数据库名称
> 
> POSTGRES_USER（环境变量）：数据库管理员用户名
> 
> POSTGRES_PASSWORD（环境变量）：数据库管理员密码

<br>

部署完成记得重启一下 `blinko-website`  容器，否则可能会连接不上 postgres 数据库。<br>

# 使用

![Snipaste_2025-10-25_22-48-18.png](https://cdn.jsdelivr.net/gh/tosspi/picgocore@main/marktext/Snipaste_2025-10-25_22-48-18.png)

部署完先注册一个账户，因为我已经注册完毕，并且关闭了允许注册，所以这里没有显示注册按钮。

![Snipaste_2025-10-25_22-50-50.png](https://cdn.jsdelivr.net/gh/tosspi/picgocore@main/marktext/Snipaste_2025-10-25_22-50-50.png)

界面还是比较好看的。

还支持AI。

![Snipaste_2025-10-25_22-51-44.png](https://cdn.jsdelivr.net/gh/tosspi/picgocore@main/marktext/Snipaste_2025-10-25_22-51-44.png)

刚部署完还没有研究，更多的可以去Github看一下：[GitHub - blinkospace/blinko: An open-source, self-hosted personal AI note tool prioritizing privacy, built using TypeScript .](https://github.com/blinkospace/blinko)

<br>

> &emsp;<font size=9 color=#7a1b0c>生命不息，折腾不止。</font>
