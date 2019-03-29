---
layout: wiki
title: 博客管理相关
categories: [博客管理]
description: 个人博客管理相关。
keywords: blog
mermaid: true
sequence: true
flow: true
mathjax: true
---

**目录**

* TOC
{:toc}


### 建站
参照[个人主页](https://github.com/buaawht/buaawht.github.io)，简述主要流程

### 使用细节
#### 本地编辑预览
以mac为例

1. 安装ruby
2. 安装bundler

    ```sh
    sudo gem install -n /usr/local/bin bundler
    ```
3. 安装jekyll
    ```sh
    sudo gem install -n /usr/local/bin jekyll
    ```
4. 运行
```sh
cd github.io的本地主目录
jekyll serve // 运行
访问http://localhost:4000即可
```
