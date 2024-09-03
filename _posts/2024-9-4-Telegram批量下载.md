---
layout:     post   			    # 使用的布局（不需要改）
title:      Telegram批量下载，不限速私密内容		# 标题 
subtitle:   教程 #副标题
date:       2024-9-4		# 时间
author:     specked2527			# 作者
header-img: img/IMG_20240613_174502_796.jpg 	#这篇文章标题背景图片
catalog:    true 				    # 是否归档
tags:		
    - 教程
  
--- 
# 介绍
https://docs.iyear.me/tdl/zh/​
不限速和可下载私密内容的Telegram批量下载器
![](https://docs.iyear.me/tdl/img/logo.png)

# 安装
https://docs.iyear.me/tdl/zh/getting-started/installation/#%e9%a2%84%e7%bc%96%e8%af%91%e4%ba%8c%e8%bf%9b%e5%88%b6

# 开始使用
在 下载解压后 文件夹 shift + 鼠标右键 选择 在此处打开powershell

#### 设置代理

输入
```
set http_proxy=http://127.0.0.1:端口号
set https_proxy=http://127.0.0.1:端口号
```
端口号是你的代理软件设置

如

set http_proxy=http://127.0.0.1:10809

以下命令都要加 ./ 开头

如

输入： ./tdl dl -u 链接

# 下载分享链接
把 链接 改为你的链接

单链接
`tdl dl -u 链接 `

多链接模式
`tdl dl -u 链接 -u 链接`

如

`tdl dl -u https://t.me/tdl/1 -u https://t.me/tdl/2`

# 想一键下载 频道 消息内的回复 可以用两条命令

```
tdl chat export -c CHAT --reply POST_ID
tdl dl -f tdl-export.json
```
CHAT改成 下载对方用户名
POST_ID改成 链接的id

#### CHAT 示例,选择一个
```
@iyear
iyear
123456789（ID）
https://t.me/iyear
+1 123456789（电话号码）
```
#### POST_ID示例
选择评论链接中的160277数字

这是两个不同的链接，注意
频道链接
https://t.me/c/1701303402/816709
评论链接
https://t.me/woshadiao/160277?comment=816759

#### 列如
```
tdl chat export -c @woshadiao --reply 160277
tdl dl -f tdl-export.json
```





