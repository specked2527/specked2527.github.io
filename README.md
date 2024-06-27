# 样式
[specked2527.github.io](https://specked2527.github.io/)  
[cdn加速版:gg.timefail.xyz](https://gg.timefail.xyz/)
# 教程
https://github.com/qiubaiying/qiubaiying.github.io/wiki/%E5%8D%9A%E5%AE%A2%E6%90%AD%E5%BB%BA%E8%AF%A6%E7%BB%86%E6%95%99%E7%A8%8B  
你也可以fork我的  

# cdn加速
能防止gfw国内打不开你的网站
* 需要购买一个域名 Name.com
* 注册cdn账户https://dash.cloudflare.com/
* 以下是简化操作 如有疑问自行搜索
  * 在Name.com删除域名dns解析>填写Cloudflare 名称服务器>
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
管理 GitHub Pages 站点的自定义域
您可以设置或更新某些 DNS 记录和仓库设置，以将 GitHub Pages 站点的默认域指向自定义域。

谁可以使用此功能？
GitHub Pages 适用于具有 GitHub Free 和组织的 GitHub Free 的公共存储库，以及具有 GitHub Pro、GitHub Team、GitHub Enterprise Cloud 和 GitHub Enterprise Server 的公共和专用存储库。 有关详细信息，请参阅“GitHub 的计划”。

从 2024 年 6 月 30 日起，所有 GitHub Pages 版本都将使用 GitHub Actions。 无需进行其他更改，但必须在存储库中启用 GitHub Actions 才能继续构建。 有关 GitHub Actions 运行器的详细信息，请参阅“管理存储库的 GitHub Actions 设置”。

Platform navigation
Mac
Windows
Linux
本文内容
关于自定义域配置
配置 apex 域
配置子域
自定义域的 DNS 记录
删除自定义域
保护自定义域
延伸阅读
拥有仓库管理员权限的人可为 GitHub Pages 站点配置自定义域。

关于自定义域配置
提示：**** 建议在将自定义域添加到存储库之前先对其进行验证，以提高安全性并避免接管攻击。 有关详细信息，请参阅“验证 GitHub Pages 的自定义域”。

使用 DNS 提供程序配置自定义域之前，请确保将自定义域添加到您的 GitHub Pages 站点。 使用 DNS 提供程序配置自定义域而不将其添加到 GitHub，可能导致其他人能够在您的某个子域上托管站点。

dig 命令可用于验证 DNS 记录的配置是否正确，它未包含在 Windows 中。 要验证 DNS 记录是否已正确配置，可以使用 Resolve-DnsName PowerShell 命令或安装 BIND。

注意：传播 DNS 更改可能需要长达 24 小时的时间。

配置 apex 域
要设置顶点域（例如 example.com），必须在存储库设置中配置自定义域，并使用 DNS 提供程序配置至少一个 ALIAS、ANAME 或 A 记录。

在 GitHub 上，导航到站点的仓库。

在存储库名称下，单击 “设置”。 如果看不到“设置”选项卡，请选择“”下拉菜单，然后单击“设置”********。

存储库标头的屏幕截图，其中显示了选项卡。 “设置”选项卡以深橙色边框突出显示。
在边栏的“代码和自动化”部分中，单击“ Pages”。

在“自定义域”下，键入自定义域，然后单击“保存”。 如果从分支发布站点，会创建一个提交，将 CNAME 直接文件添加到源分支的根目录。 如果使用自定义 GitHub Actions 工作流发布网站，则不会创建任何 CNAME 文件，因此需要手动创建一个（仅包含自定义域的文本行）。 有关发布源的详细信息，请参阅“配置 GitHub Pages 站点的发布源”。

导航到 DNS 提供程序并创建一条 ALIAS、ANAME 或 A 记录。 还可以为 IPv6 支持创建 AAAA 记录。 如果要实现 IPv6 支持，我们强烈建议在 AAAA 记录之外使用 A 记录，因为 IPv6 的全局采用速度缓慢。 有关如何创建正确记录的更多信息，请参阅 DNS 提供程序的文档。

要创建 ALIAS 或 ANAME 记录，请将顶点域指向站点的默认域。 有关站点的默认域的详细信息，请参阅“关于 GitHub Pages”。

要创建 A 记录，请将顶点域指向 GitHub Pages 的 IP 地址。

185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
要创建 AAAA 记录，请将顶点域指向 GitHub Pages 的 IP 地址。

2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
警告：我们强烈建议勿使用通配符 DNS 记录，例如 *.example.com。 即使验证域，这些记录也会立即面临域接管风险。 例如，如果验证 example.com，这会阻止某人使用 a.example.com，但他们仍可以接管 b.a.example.com（由通配符 DNS 记录所涵盖）。 有关详细信息，请参阅“验证 GitHub Pages 的自定义域”。

打开Git Bash。

要确认 DNS 记录配置正确，请使用 dig 命令，将 EXAMPLE.COM 替换为顶点域。 确认结果与上面 GitHub Pages 的 IP 地址相匹配。

适用于 A 记录：

$ dig EXAMPLE.COM +noall +answer -t A
> EXAMPLE.COM    3600    IN A     185.199.108.153
> EXAMPLE.COM    3600    IN A     185.199.109.153
> EXAMPLE.COM    3600    IN A     185.199.110.153
> EXAMPLE.COM    3600    IN A     185.199.111.153
适用于 AAAA 记录：

$ dig EXAMPLE.COM +noall +answer -t AAAA
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8000::153
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8001::153
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8002::153
> EXAMPLE.COM     3600    IN AAAA     2606:50c0:8003::153
请记住还要检查 A 记录。

如果你使用静态站点生成器在本地构建站点并将生成的文件推送到 GitHub，请将添加 CNAME 文件的提交拉取到本地存储库。 有关详细信息，请参阅“自定义域和 GitHub Pages 疑难解答”。

（可选）若要为站点强制实施 HTTPS 加密，请选择“强制实施 HTTPS”。 可能要过 24 小时才能使用此选项。 有关详细信息，请参阅“使用 HTTPS 保护 GitHub Pages 站点”。

配置顶点域和 www 子域变体
注意：**** 建议为 HTTPS 安全网站设置 www 子域以及顶点域。

如果使用 apex 域作为自定义域名，建议还设置一个 www 子域。 如果通过 DNS 提供程序配置每种域类型的正确记录，GitHub Pages 将自动在域之间创建重定向。 例如，如果将 www.example.com 配置为站点的自定义域，并且为顶点和 www 域设置了 GitHub Pages DNS 记录，则 example.com 将重定向到 www.example.com。 请注意，自动重定向仅适用于 www 子域。 自动重定向不适用于任何其他子域，如 blog。 有关详细信息，请参阅“配置子域”。

导航到 DNS 提供程序并为指向 GitHub Pages 默认域的 www 子域创建一条 CNAME 记录。 例如，假设网站位于 <user>.github.io，则应创建一条将 www.example.com 指向 <user>.github.io 的 CNAME 记录。同样，对于位于 <organization>.github.io 的组织网站，应创建一条将 www.example.com 指向 <organization>.github.io 的 CNAME 记录。 确保 CNAME 记录直接指向 <user>.github.io 或 <organization>.github.io，而不包含存储库名称。

有关如何创建正确记录的更多信息，请参阅 DNS 提供程序的文档。 有关站点的默认域的详细信息，请参阅“关于 GitHub Pages”。

配置子域
要设置 www 或自定义子域（例如 www.example.com 或 blog.example.com），必须在存储库设置中添加你的域。 然后，通过 DNS 提供商配置 CNAME 记录。

在 GitHub 上，导航到站点的仓库。

在存储库名称下，单击 “设置”。 如果看不到“设置”选项卡，请选择“”下拉菜单，然后单击“设置”********。

存储库标头的屏幕截图，其中显示了选项卡。 “设置”选项卡以深橙色边框突出显示。
在边栏的“代码和自动化”部分中，单击“ Pages”。

在“自定义域”下，键入自定义域，然后单击“保存”。

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
