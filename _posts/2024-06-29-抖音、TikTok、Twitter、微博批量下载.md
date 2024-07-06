---
layout:     post   			    # 使用的布局（不需要改）
title:      抖音、TikTok、Twitter、微博批量下载				# 标题 
subtitle:   教程 #副标题
date:       2024-06-29			# 时间
author:     specked2527			# 作者
header-img: img/IMG_20240613_174502_796.jpg 	#这篇文章标题背景图片
catalog:    true 				    # 是否归档
tags:		
- 教程		   #标签
    
--- 

[github版本显示](https://github.com/specked2527/specked2527.github.io/blob/master/_posts/2024-06-29-%E6%8A%96%E9%9F%B3%E3%80%81TikTok%E3%80%81Twitter%E3%80%81%E5%BE%AE%E5%8D%9A%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BD.md)
[官网](https://johnserf-seed.github.io/f2/)
[常见问题与解决办法](https://johnserf-seed.github.io/f2/question-answer/qa.html)
<img src='https://github.com/Johnserf-Seed/f2/assets/40727745/82644596-7eca-48ec-91b0-3c5e4c24ee90'>


# 开始之前
- 必须安装Python 版本≥3.8.2 https://www.python.org/downloads/
* 并添加环境变量Python
  * 如果你安装Python时忘记勾选
    * - [x] Add Python.exe to PATH。 https://blog.csdn.net/l15668952150/article/details/124571667

# 安装方式
选择一个
1. 打开powershell 输入
```py
 pip install f2    
``` 
更新
`pip install -U f2 `

2. 手动下载
在[版本](https://github.com/Johnserf-Seed/f2/releases)下载[.whl](https://github.com/Johnserf-Seed/f2/releases/download/v0.0.1.6/f2-0.0.1.6-py3-none-any.whl) 
* 在下载[.whl]的文件夹,键盘 shift + 鼠标右键，选择 在此处打开powershell 
输入
`pip install f2-0.0.1.6-py3-none-any.whl`

如果出现任何报错,尝试更新python或pip版本
* `pip install -i https://pypi.tuna.tsinghua.edu.cn/simple f2`

# 登入方式 
   * 你需要登入才能下载，在edge浏览器登入抖音后，完全关闭浏览器，注意右下角托盘图标里面的edge也要全部关闭
    输入 `f2 dy -c app.yaml --auto-cookie edge`

# 使用方式
#### `f2 dy -c dy.yaml -u ""`
  1. 单链接下载
  * 左下角windows图标右键打开powershell，输入`f2 dy --init-config dy.yaml` 
    在你的powershell显示的 PS C:\Users\x> 位置在这里的dy.yaml 用记事本打开
    把 `mode: null` 改为 `mode: one` 保存 
    * powershell 输入 `f2 dy -c dy.yaml -u ""`
      回车后 按下回车旁边的方向键↑ （你就可以每次按下回车旁边的方向键↑掉用了）
      输入 `f2 dy -c dy.yaml -u "链接"`
      
      如  `f2 dy -c dy.yaml -u "5.30 01/22 L@W.zg gOx:/ 庭中三千梨花树 再无一朵入我心。# 和服👘 # 和服少女  https://v.douyin.com/i6DHBfdx/ 复制此链接，打开Dou音搜索，直接观看视频！" `

  2. 主页批量下载
     * 把dy.yaml 的 `mode: null` 改为 `mode: post` 保存
       输入 `f2 dy -c dy.yaml -u "把主页的链接，按鼠标右键粘贴到这里"` 

  3. 喜欢页批量下载 
     * 把dy.yaml 的 `mode: null` 改为 `mode: like` 保存
       输入 `f2 dy -c dy.yaml -u "把喜欢页的链接，按鼠标右键粘贴到这里"` 

  4. 直播下载
     * 把dy.yaml 的 `mode: null` 改为 `mode: live` 保存
       输入 `f2 dy -c dy.yaml -u "把直播的链接，按鼠标右键粘贴到这里"` 

  你可以把dy.yaml 的模式`mode: one` `mode: post` `mode: like` `mode: live`分别保存为4个文件 名字随意
  * 如 1.yaml 2··3·· 
    * 下载时就选某个模式的文件 `f2 dy -c 1.yaml -u "把链接，按鼠标右键粘贴到这里"`
      
***      

#### `f2 dy -c dy.yaml -M one -u ""`
 * 可以临时改变dy.yaml设置的下载模式 `-M one` `-M post` `-M like` `-M live`
   * 如单链接下载  `f2 dy -c dy.yaml -M one -u ""`
     
   

#### `f2 dy -c dy.yaml -u ""`和`f2 dy -M one -u ""` 
* 这俩非常相似
  * `f2 dy -c dy.yaml -M one -u ""`可以临时改变dy.yaml设置的下载模式
  * `f2 dy -M one -u "" -c dy.yaml`可以使用你的dy.yaml,而不使用应用默认app.yaml
    * 注意：-M one或- M 其他模式，会临时覆盖你dy.yaml的下载设置模式

***   

# 另外一种方式 
#### `f2 dy -M one -u ""`             
 * 使用参数 `-M one -M post -M like -M collection` 更多详情输入 `f2 dy -h` 查看
   * 如 单链接下载 `f2 dy -M one -u ""`
     
#### `f2 dy -c dy.yaml`
  * 在dy.yaml 根据你的模式 这里是下载主页 `mode: post` ,把 `url: null`改为 `url: 把主页的链接，按鼠标右键粘贴到这里` 保存
    * 输入 `f2 dy -c dy.yaml` 就可以直接下载主页 其他模式也是如此
      
#### `f2 dy -u ""`      
  * 在app.yaml 根据你的模式 这里是单链接 `mode: one`,在`douyin:`下面 按格式添加 
    ```py
        mode: one
        interval: all
    ```
       * 输入 `f2 dy -u "链接"` 就可以直接下载单链接 其他模式也是如此 
         * 配置文件的位置 你可以在x:\xxxxxxx\Python\Lib\site-packages\f2\conf\文件夹中找到它们。
           * `pip show f2`展示配置文件的位置           
  
# 配置文件
#### yaml
* 配置文件由三部分组成，应用默认(app.yaml)，F2配置文件(conf.yaml)，程序默认配置文件(defaults.yaml)。
  * 应用默认(app.yaml)：用来保存所有应用不常变动的配置，例如的cookie、文件名模板、下载路径、连接超时时间、超时重试次数等。
  * F2配置文件(conf.yaml)：用来保存F2的配置，例如不同应用的计算参数和代理
  * 程序默认配置文件(defaults.yaml)：用来保存各个app的初始化默认配置模板，***请不要修改与使用它。***
* 自定义yaml
  * 你可以根据喜好选择，使用应用默认(app.yaml)，还是你创建的yaml
    * `f2 应用 --init-config 随意文件名.yaml`
      * 如 `f2 wb --init-config wb.yaml`
* 当你使用自定义文件.yaml
  * `f2 dy -c dy.yaml -u ""`
* 当你使用应用默认(app.yaml)
  * `f2 dy -u ""`
    
# 注意 
####  [SSL: WRONG_VERSION_NUMBER] 

wrong version number (_ssl.c:1007)
* v2rayn把链接阻止了
* 设置pac代理模式,或者把被阻止链接添加到路由规则直连
    
# 代理软件设置
* 如果只下载抖音，微博,就暂时把它关掉 
   * 不然你就要设置conf.yaml文件，配置文件的位置 你可以在x:\xxxxxxx\Python\Lib\site-packages\f2\conf\文件夹中找到它们。
   * `pip show f2`展示配置文件的位置
     
> 你可以看到每个 应用: 都有`proxies:`,你需要哪个代理就填哪个应用

   把 `proxies:` 改成 
```py
proxies:
      http://: http://127.0.0.1:10809
      https://: http://127.0.0.1:10809
```
   :10809是我的代理端口，你要填你自己的，自行搜索你的代理软件默认端口
 
# 其他 
#### 除了抖音，TikTok、Twitter、微博也是同样的操作下载
 * 输入 `f2 -h` 就能看到对应的缩写 
   * 如 `f2 wb` 就能看到对应的说明
* 每个应用都要输入一次`f2 应用 --init-config 随意文件名.yaml`
  * 创建yaml文件后，就不用再次输入
    * 如 `f2 wb --init-config wb.yaml`
* 不这么做的话你就只能使用
  *  `f2 应用 -M 模式 -u "链接"`
    * 如 `f2 wb -M one -u ""`
* 每个应用你还需要登入网站,记得吗?
  * 输入 `f2 应用 -c app.yaml --auto-cookie edge`
    * 如 `f2 wb -c app.yaml --auto-cookie edge`

#### 如果出现类似 `Error: No such command 'lrb'`
 * 这说明这功能还没有写，不能用
 
# 你还可以在手机上使用
 电脑安装配置后可以在手机使用（电脑安装ssh服务，手机安装ssh软件如JuiceSSH，打电脑开文件共享，手机安装es文件管理，或其他文件软件，就可以查看在电脑的下载文件
 ![343198751-27d559ad-f9a2-4ac1-a830-fe566118cd95.jpg](https://s2.loli.net/2024/06/29/uGYINLkwzCZTRDP.jpg)

# 警告 
当你使用任何批量下载软件时 
Cookie 会用于包括获取信息在内的所有 API 请求中。软件的请求与浏览器内正常使用所发送的请求不完全一致，能通过分析请求日志识别出来。
 软件开发者不对账号发生的任何事情负责，包括并不限于被标记为机器人账号、被冻结、无法参与各种活动等。建议使用小号。
 如您知晓您的账号会因以上所列出来的部分原因所导致无法使用或权益受损等情况，并愿意承担由此所会带来的一系列后果，请继续以下的操作，软件开发者不会对您账号所发生的任何后果承担责任。
