---
layout:     post   			    # 使用的布局（不需要改）
title:      批量下载视频bilibili-youtube和1821个网站		# 标题 
subtitle:   教程 #副标题
date:       2024-7-3		# 时间
author:     specked2527			# 作者
header-img: img/IMG_20240613_174502_796.jpg 	#这篇文章标题背景图片
catalog:    true 				    # 是否归档
tags:		
- 生活		   #标签
    
--- 

[支持1821个网站](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md)

# 1. 下载 yt-dlp.exe
https://github.com/yt-dlp/yt-dlp/tags

# 2. 下载 get-cookiestxt-locally
https://chrome.google.com/webstore/detail/get-cookiestxt-locally/cclelndahbckbenkjhflpdbgdldlbecc 

# 登入你要下载的视频网站，get-cookiestxt-locally 点击齿轮图标，设置导出 Mozilla/Netscape 格式。 
鼠标右键新建一个文本文档.txt，粘贴你刚刚复制的cookie 保存，  保存后改名为cookies.txt,注意不是cookies.txt.txt

# 3. 使用
在yt-dlp 文件夹 shift + 鼠标右键 选择 在此处打开powershell

#### 下载视频
`yt-dlp 链接/投稿主页链接`

如 `yt-dlp  https://www.bilibili.com/video/BV1df4y1i7yi/`

#### 下载音乐
`yt-dlp 链接 -F `

如 `yt-dlp https://www.bilibili.com/video/BV1df4y1i7yi/ -F `
* 根据ID数字，选择audio only，FILESIZE最大的那个
  * yt-dlp 链接 -f 那个数字
    * 在相同的网站下，这个数字是固定的
    * 如 `yt-dlp https://www.bilibili.com/video/BV1df4y1i7yi/ -f 30280 `

如果报错
把链接加上英语的""
如 `yt-dlp  "https://www.bilibili.com/video/BV1df4y1i7yi"`

# 配置
把cookies.txt放在在yt-dlp.exe文件夹，新建一个文本.txt

填写你的cookie.txt路径,并删除我留下的中文，如--cookies "c:/1/cookie.txt"
* 填写以下内容,保存修改文件名为yt-dlp.conf
```
-o ./yt/%(title)s.%(ext)s
--cookies "你的cookie.txt路径 如c:/1/cookie.txt"
```

# 保存位置
在你的PowerShell 显示
PS C:\Users\x> 的地方，文件夹在yt
