---
title: Butterfly主题快速入门
categories: 零零散散
tags:
 - Hexo
 - Hexo-theme
---

> 此战针对 butterfly 主题使用时进行的修改以及配置

<!-- more -->

## 一、文章页面

### 1. Front-matter

#### 1.1 Page Front-matter

```markdown
---
title:
date:
updated:
type:
comments:
description:
keywords:
top_img:
mathjax:
katex:
aside:
aplayer:
highlight_shrink
---
```

|             写法 | 解释                                                         |
| ---------------: | :----------------------------------------------------------- |
|            title | 【必选】页面标题                                             |
|             date | 【必选】页面创建日期                                         |
|             type | 【必选】标签、分类和友情链接三个页面需要配置                 |
|          updated | 【可选】页面更新日期                                         |
|      description | 【可选】页面描述                                             |
|         keywords | 【可选】页面关键字                                           |
|         comments | 【可选】显示页面评论模块（默认true）                         |
|          top_img | 【可选】页面顶部图片                                         |
|            aside | 【可选】页面侧边栏（默认true）                               |
| highlight_shrink | 【可选】配置代码框是否展开（true/false）（默认为设置中highlight_shrink的配置） |

#### 1.2 POST Front-matter

```markdown
---
title:
date:
updated:
tags:
categories:
keywords:
description:
top_img:
comments:
cover:
toc:
toc_number:
toc_style_simple:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
mathjax:
katex:
aplayer:
highlight_shrink:
aside:
---
```

|                  写法 | 解释                                                         |
| --------------------: | :----------------------------------------------------------- |
|                 title | 【必选】页面标题                                             |
|                  date | 【必选】页面创建日期                                         |
|               updated | 【可选】页面更新日期                                         |
|                  tags | 【可选】文章标签                                             |
|            categories | 【可选】文章分类                                             |
|              keywords | 【可选】文章关键字                                           |
|           description | 【可选】文章描述                                             |
|               top_img | 【可选】文章顶部图片                                         |
|                 cover | 【可选】文章缩略图（如果没有设置top_img，文章页顶部将展示缩略图，可设置flase/图片地址/留空） |
|              comments | 【可选】展示文章评论模块（默认true）                         |
|                   toc | 【可选】展示文章TOC（默认为设置中toc的enable配置）           |
|            toc_number | 【可选】展示toc_number（默认为设置中toc的number配置）        |
|      toc_style_simple | 【可选】展示toc简洁模式                                      |
|             copyright | 【可选】展示文章版权模块（默认为设置中post_copyright的enable配置） |
|      copyright_author | 【可选】文章版权模块的`文章作者`                             |
| copyright_author_hlef | 【可选】文章版权模块的`文章作者`链接                         |
|         copyright_url | 【可选】文章版权模块的`文章连接`链接                         |
|        copyright_info | 【可选】文章版权模块的`版权声明`文字                         |

### 2. 标签页

`hexo new page tags`

```markdown
---
title: 标签
date:
type: "tags"
---
```

### 3. 分类页

`hexo new page categories`

```markdown
---
title: 分类
date:
type: "categories"
---
```

### 4. 置顶文章

hexo-generator-index从 2.0.0 开始，已经支持文章置顶功能。你可以直接在文章的front-matter区域里添加`sticky: 1`属性来把这篇文章置顶。数值越大，置顶的优先级越大。

## 二、主题配置

### 1. 基础配置

_config.yml

设置中文：`language: zh_CN`

设置网站标题：`title: Moekylin`

设置网站副标题：`subtitle: 77`

设置文章作者：`author: 77`

### 2. 主题配置

_config.butterfly.yml

#### 2.1 导航菜单

```yaml
menu:
  首页: / || fas fa-home
  文章: /archives/ || fas fa-archive
  标签: /tags/ || fas fa-tags
  分类: /categories/ || fas fa-folder-open
  # List||fas fa-list:
  #   Music: /music/ || fas fa-music
  #   Movie: /movies/ || fas fa-video
  # Link: /link/ || fas fa-link
  关于: /about/ || fas fa-heart
```

#### 2.2 其他配置

取消自动换行：

_config.yml

```yaml
highlight:
  enable: true
  line_number: false	# 修改此处为 false
  auto_detect: false
  tab_replace: ''
  wrap: true
  hljs: false
```

_config.butterfly.yml

```yaml
code_word_wrap: true
```

```python
import sys
print('曾经富丽堂皇的古行宫已是一片荒凉冷落，宫中艳丽的花儿在寂寞寥落中开放。幸存的几个满头白发的宫女，闲坐无事只能谈论着玄宗轶事。')
for i in range(1,254):
  print(i)
```

#### 2.3 社交图标

```
social:
	fab fa-github: https://github.com/moekylin || Github
```

图标库：https://fontawesome.com/icons

#### 2.4 顶部图

隐藏顶部图

```yaml
disable_top_img: true
```

#### 2.5 社交头像

```yaml
avatar:
  img: https://s2.loli.net/2022/07/12/TutXzSjQ2EPoNKs.png
  effect: false
```

#### 2.6 首页文章显示 tags

```yaml
post_meta:
  page: # Home Page
    tags: true # true or false 主頁是否顯示標籤 <- 修改此条
```

#### 2.7 文章封面禁用

```yaml
cover:
  # display the cover or not (是否顯示文章封面)
  index_enable: false
  aside_enable: false
  archives_enable: false
```

#### 2.8 TOC设置

```yaml
toc:
  post: true
  page: false
  number: false # 禁用显示章节数
  expand: true # 自动展开 toc
  style_simple: true # 简洁模式 侧边栏只显示 toc  
```

#### 2.9 关闭上/下一篇文章

```yaml
post_pagination: false
```

#### 2.10 侧边栏设置

```yaml
aside:
  position: left # 左侧显示侧边栏
  card_tags:
    color: true # 开启标签颜色
```

#### 2.11 资讯显示运行时间

```yaml
runtimeshow:
  enable: true
  publish_date: 7/12/2022 00:00:00
```

#### 2.12 开启搜索功能

1. 安装插件

```
$ npm install hexo-generator-search --save
```

2. _config.butterfly.yml

```yaml
local_search:
  enable: true
  preload: false
  CDN:
```

### 3. 侧边栏(aside:)设置

#### 3.1 隐藏公告

```yaml
  card_announcement:
    enable: false
    content: This is my Blog
```

#### 3.2 隐藏最新文章

```yaml
  card_recent_post:
    enable: false
    limit: 5 # if set 0 will show all
    sort: date # date or updated
    sort_order: # Don't modify the setting unless you know how it works
```

### 4. 图片设置

#### 4.1 博客背景

```yaml
background: url(https://s2.loli.net/2022/07/12/2bA6GnVEcR5foqL.png)
```

#### 4.2 背景飘带

```yaml
# Fluttering Ribbon (动态彩带)
canvas_fluttering_ribbon:
  enable: true
  mobile: false
```

#### 4.3 点击烟花

```yaml
# Mouse click effects: fireworks (鼠标点击效果: 烟花特效)
fireworks:
  enable: true
  zIndex: 9999 # -1 or 9999
  mobile: false
```

废档
