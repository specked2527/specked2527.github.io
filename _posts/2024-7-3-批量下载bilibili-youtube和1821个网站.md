---
layout:     post   			    # 使用的布局（不需要改）
title:      批量下载bilibili-youtube和1821个网站		# 标题 
subtitle:   yt-dlp.exe #副标题
date:       2024-7-3		# 时间
author:     specked2527			# 作者
header-img: img/IMG_20240613_174502_796.jpg 	#这篇文章标题背景图片
catalog:    true 				    # 是否归档
tags:		
- 教程	   #标签
    
--- 

[支持1821个网站](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md)
[官网](https://github.com/yt-dlp/yt-dlp/)

![p](https://raw.githubusercontent.com/yt-dlp/yt-dlp/master/.github/banner.svg)

# 1. 下载 yt-dlp.exe
https://github.com/yt-dlp/yt-dlp/tags

# 2. 下载 get-cookiestxt-locally
https://chrome.google.com/webstore/detail/get-cookiestxt-locally/cclelndahbckbenkjhflpdbgdldlbecc 

# 登入你要下载的视频网站，get-cookiestxt-locally 点击齿轮图标，设置导出 Mozilla/Netscape 格式。 
鼠标右键新建一个文本文档.txt，粘贴你刚刚复制的cookie 保存，  保存后改名为cookies.txt,注意不是cookies.txt.txt

# 配置
把cookies.txt放在在yt-dlp.exe文件夹，新建一个文本.txt

填写你的cookie.txt路径,并删除我留下的中文，如--cookies "c:/1/cookie.txt"
* 填写以下内容,保存修改文件名为yt-dlp.conf
```
-o ./yt/%(title)s.%(ext)s
--cookies "你的cookie.txt路径 如c:/1/cookie.txt"
```


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


# 保存位置
在你的PowerShell 显示
PS C:\Users\x> 的地方，文件夹在yt

# 你还可以在手机上使用
 电脑安装配置后可以在手机使用
 （电脑安装OpenSSH Server，手机安装ssh软件JuiceSSH，
 
  打电脑开文件共享，手机安装es文件管理，或其他文件软件，就可以查看/复制在电脑的下载文件到手机上）

# 添加环境变量
就可以在PowerShell，直接输入XXX运行了 
* 你可以把xxx.exe改名为aaa.exe,输入时就是aaa了 如'gallery-dl.exe'改为`a.exe`
  * 把XXX.exe程序所在的文件夹，添加环境变量
    * - [x] 参考操作 https://blog.csdn.net/l15668952150/article/details/124571667

# 警告 
当你使用任何批量下载软件时 
Cookie 会用于包括获取信息在内的所有 API 请求中。软件的请求与浏览器内正常使用所发送的请求不完全一致，能通过分析请求日志识别出来。
 软件开发者不对账号发生的任何事情负责，包括并不限于被标记为机器人账号、被冻结、无法参与各种活动等。建议使用小号。
 如您知晓您的账号会因以上所列出来的部分原因所导致无法使用或权益受损等情况，并愿意承担由此所会带来的一系列后果，请继续以下的操作，软件开发者不会对您账号所发生的任何后果承担责任。
