---
title: Typora上传bilibili图床
categories: 零零散散
tags:
 - Typora
 - 图床
---

> typora配合hexo写作时我们会面临着图片上传的问题，如果你上传的图片文件在笔记的文件夹内，那么在网页渲染时会花费大量的时间，这也导致了文章的访问速度缓慢，为解决这一问题，本站采用typora+bilibili图床上传方案，插件下载地址已置于文末。

<!-- more -->

### 1. 下载插件

下载后将插件放到 typora 目录

Mac 下 Typora 目录：打开访达，左侧选择应用程序，找到 typora 右键，显示包内容，依次进入 Contents -> Resources 即可

### 2. 获取 token

2.1 进入 www.bilibili.com 页面，按 F12 打开调试工具

2.2 依次点击 应用 -> Cookie -> https://www.bilibili.com

2.3 右侧找到 SESSDATA 保留 value 内容

![image-20220712194230455](https://i0.hdslb.com/bfs/album/4d11fa0a71449970821d25fce587402ec3ac1984.png)

### 3. 配置 Typora

3.1 打开 Typora 图像设置

3.2 设置 `插入图片时...` 为上传图片，`上传服务`选择 Custom Command，命令为 `main绝对路径`

```
/Users/xxx/bilibili/typora-plugin-bilibili-macos token=你的SESSDATA # Mac
D:\Downloads\typora-plugin-bilibili-win.exe token=你的SESSDATA # Windows
```

3.3 设置完成后点击验证图片上传选项，若出现验证成功，此时便可以通过直接粘贴图片到 Typora 内的方式上传图片

### 4. 注意事项

如遇到上传失败等情况则可能是 token 值变更，需要回到第二步获取 token，并更新 typora 内的token，这个方式的弊端很明显，hexo 博客也无法正常解析图片地址，只有在本地的 typora 内可以正常查看，并且如果b站的图床链接修改，那么我们也会遇到图片链接全部失效等情况，在选择图床时，如果只有在本地markdown文档内插入图片的需求，并且图片数量并不多，可以采纳这个方案。反之则并不是首选。

参考资料

typora-plugin-bilibili：https://github.com/xlzy520/typora-plugin-bilibili

