# 样式
[specked2527.github.io](https://specked2527.github.io/)  
[cdn加速版:gg.timefail.xyz](https://gg.timefail.xyz/)  

如果不喜欢 自己搜索其他的 如
https://github.com/lemonchann/lemonchann.github.io

# 教程
https://github.com/qiubaiying/qiubaiying.github.io/wiki/%E5%8D%9A%E5%AE%A2%E6%90%AD%E5%BB%BA%E8%AF%A6%E7%BB%86%E6%95%99%E7%A8%8B  
你也可以fork我的  

# cdn加速
能防止gfw国内打不开你的网站
* 需要购买一个域名 Name.com
* 注册cdn账户https://dash.cloudflare.com/

以下是简化操作 如有疑问自行搜索
  * 在Name.com删除域名dns解析>填写Cloudflare 名称服务器
  * 在Cloudflare dns添加>
```
类型
CNAME
名称 （必需）
gg  (填你的)
root 使用 @
目标 （必需）
specked2527.github.io (填你的)
```
管理自定义域
在 GitHub 上，导航到站点的仓库。

> 在存储库名称下，单击 “设置”。 如果看不到“设置”选项卡，请选择“”下拉菜单，然后单击“设置”********。
>
> 存储库标头的屏幕截图，其中显示了选项卡。 “设置”选项卡以深橙色边框突出显示。
在边栏的“代码和自动化”部分中，单击“ Pages”。
>
> 在“自定义域”下，键入自定义域，然后单击“保存”。 如`gg.timefail.xyz`  
>
> 参考https://docs.github.com/zh/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site?platform=windows#configuring-a-subdomain
>

# 补充
PC网页模式 右上角About 的齿轮图标  可以设置你的地址 [specked2527.github.io](https://specked2527.github.io/)  

如何写文章？https://markdown.com.cn/basic-syntax/ 
* 在 _posts 的文件夹中。创建一个新文件 
  * 每一篇文章文件命名采用的是`2017-02-04-Hello-2017.md`时间+标题的形式，空格用-替换连接。
文件的格式是 .md
每个文件开头要填写以下格式
```
---
layout:     post   				    # 使用的布局（不需要改）
title:      My First Post 				# 标题 
subtitle:   Hello World, Hello Blog #副标题
date:       2017-02-06 				# 时间
author:     BY 						# 作者
header-img: img/post-bg-2015.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 生活
---

## halo~
>这是你的第一篇博客。

进入你的博客主页，新的文章将会出现在你的主页上.
```
在 img 文件夹中可以上传图片 在 header-img: img/这里填写图片名称.jpg 
* 主页、关于、标签的背景图也是如此 如about.html、 tags.html
* 你的github最大只有1 GB容量，所以图片上传前最好先压缩
