---
layout:     post   			    # 使用的布局（不需要改）
title:      抖音、TikTok、Twitter、微博 批量下载				# 标题 
subtitle:   教程 #副标题
date:       2024-06-29			# 时间
author:     specked2527			# 作者
header-img: img/IMG_20240613_174502_796.jpg 	#这篇文章标题背景图片
catalog:    true 				    # 是否归档
tags:		
- 生活		   #标签
    
--- 

# 开始之前
- 必须安装Python 版本≥3.8.2 https://www.python.org/downloads/
* 并添加环境变量Python
  * 如果你安装Python时忘记勾选
    * - [x] Add Python.exe to PATH。 https://blog.csdn.net/l15668952150/article/details/124571667

# 安装方式 

1. 打开powershell 输入
```
 pip install f2    
``` 
更新
`pip install -U f2 `

2. 手动下载
在[版本](https://github.com/Johnserf-Seed/f2/releases)下载[.whl](https://github.com/Johnserf-Seed/f2/releases/download/v0.0.1.6/f2-0.0.1.6-py3-none-any.whl) 

在下载[.whl]的文件夹,键盘 shift + 鼠标右键，选择 在此处打开powershell 

输入
`pip install f2-0.0.1.6-py3-none-any.whl`

# 使用方式 

  1. 单链接下载
  * 左下角windows图标右键打开powershell 输入`f2 dy --init-config dy.yaml` 
    在你的powershell显示的 PS C:\Users\x> 位置在C:\Users\x\ 这里的dy.yaml 用记事本打开
    把`mode: null` 改为 `mode: one` 保存 
    * powershell 输入`f2 dy -c dy.yaml -u ""` 回车后 按下回车旁边的方向键↑ （你就可以每次按下回车旁边的方向键↑掉用了）
      输入 `f2 dy -c dy.yaml -u "把要下载的链接，按鼠标右键粘贴到这里"`
      如  `f2 dy -c dy.yaml -u "5.30 01/22 L@W.zg gOx:/ 庭中三千梨花树 再无一朵入我心。# 和服👘 # 和服少女  https://v.douyin.com/i6DHBfdx/ 复制此链接，打开Dou音搜索，直接观看视频！" `

  2. 主页批量下载
     * 把dy.yaml 的 `mode: null` 改为 `mode: post` 保存
       输入 `f2 dy -c dy.yaml -u "把主页的链接，按鼠标右键粘贴到这里"` 

  3. 喜欢页批量下载 
     * 把dy.yaml 的 `mode: null` 改为 `mode: like` 保存
       输入 `f2 dy -c dy.yaml -u "把主页的链接，按鼠标右键粘贴到这里"` 

  4. 直播下载
     * 把dy.yaml 的 `mode: null` 改为 `mode: live` 保存
       输入 `f2 dy -c dy.yaml -u "把直播的链接，按鼠标右键粘贴到这里"` 

  你可以把模式`mode: post` `mode: like` `mode: live`分别保存为3个文件 名字随意
  * 如 1.yaml 2··3·· 
    * 下载时就选某个模式 `f2 dy -c 1.yaml -u "把主页的链接，按鼠标右键粘贴到这里"` 

  另外一种方式 
  * 在dy.yaml 根据你的模式 `mode: post` 把 `url: null`改为 `url: 把主页的链接，按鼠标右键粘贴到这里` 保存
    * 输入 `f2 dy -c dy.yaml` 就可以直接下载 

 # 登入方式 
 
   * 你需要登入才能下载，在edge浏览器登入抖音后，完全关闭浏览器，注意右下角托盘图标里面的也要全部关闭
    输入 `f2 dy -c app.yaml --auto-cookie edge` 

 # 注意 
 
   * 代理软件设置，如果只下载抖音，就暂时把它关掉 
   不然你就要设置conf.yaml文件，配置文件的位置 你可以在x:\xxxxxxx\Python\Lib\site-packages\f2\conf\文件夹中找到它们。
   * `pip show f2`展示配置文件的位置 

   把 `proxies:` 改成 
```py
proxies:
      http://: http://127.0.0.1:10809
      https://: http://127.0.0.1:10809
```
   :10809是我的代理端口，你要填你自己的，自行搜索你的代理软件默认端口

 # 其他 
 
 除了抖音，TikTok、Twitter、微博也是同样的操作下载
 * 输入 `f2 -h` 就能看到对应的缩写 
   * 如 `f2 wb` 就能看到对应的说明 
 如果出现 `Error: No such command 'lrb'`
 * 这说明这功能还没有写，不能用

 # 你还可以在手机上使用

 电脑安装配置后可以在手机使用（电脑安装ssh服务，手机安装ssh软件如JuiceSSH，打电脑开文件共享，手机安装es文件管理，或其他文件软件，就可以查看在电脑的下载文件
 ![343198751-27d559ad-f9a2-4ac1-a830-fe566118cd95.jpg](https://s2.loli.net/2024/06/29/uGYINLkwzCZTRDP.jpg)
