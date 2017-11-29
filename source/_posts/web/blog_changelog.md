title: 折腾个人博客
date: 2017-07-05
updated: 2017-07-08
categories: [web]
tags: [web]
description: Blog Changelog&#58; 博客变更日志，以及《搭建个人博客》的详细拓展。
---

## 说明

- 这只是个一文不名的独立博客，但折腾它是博主的一种乐趣（消遣）。
- 前文《[搭建个人博客](/web/build_blog/)》只是简单说明了建站过程和定制点。
- 本文《折腾个人博客》作为本博客今后的__「变更日志」__；
    - 也会回溯本博客的演变过程，简述具体做法及其考量；
    - 顺便展开讲讲前文中提及的「定制点」（可折腾的东西）。

---

## 变更日志

- __折腾日志__

### 2017.01 ~ 07

- 修改 PV 数的显示方式
    - 由准确数，改为模糊数：`1024` 显示 `1.0 k +`
- 改用 Disqus 评论系统
    - 由于 多说 关停服务，将评论数据全部导出后，修正内容、转换格式后，导入至 Disqus
- 网站内容汉化
    - 清理、简化 所有文章所有夹英夹中的博客主题文案和文章内容（假洋鬼子的文风并不好…）
- 加速 网站访问
    - 停用 Google Analytics，只用 百度统计
    - 停用 Google Fonts，改用 css.net 的字体资源
    - 使用 Hexo Plugin [hexo-all-minifier](https://github.com/chenzhutian/hexo-all-minifier)
        - 压缩 页面及其引用资源的占用的存储空间大小
    - 使用 BootCDN 的 `*.min.js` `*.min.css` 资源，替换所有相关开源包的 `*.js` `*.css`
        - 相关资源传输耗时从 100 ms+ 下降到 100 ms-
    - 点击 才去加载 Disqus 的所有相关资源
- 简化 404 页面
    - 简化 显示的文本
    - 去掉 错误链接重定向
    - 去掉 错误链接的收集
- 显示效果
    - 添加 每篇文章的字数统计，及其 显示
    - 添加 CC 3.0 的署名协议声明到每篇文章的末尾
    - 添加 社交网络的链接到边栏
    - 提高 每页显示文章数量上限
    - 简化 显示文章的发布日志和更新日志
        - 只显示一个日期
        - 优先显示文章的更新日期
        - 如无显示文章的发布日期
    - 简化 边栏「热榜」模块的显示元素
    - 添加 边栏「热榜」模块的动画效果
    - 去掉 每篇文章下的百度分享按钮
    - ~~开启 Hexo Theme NexT 的博客背景 Canvas-nest 动效~~
        - PC 浏览器的效果不错，但移动端的效果太显眼，影响页面浏览，遂关
- 优化 用于博客文章的 PV 统计的 LeanCloud 调用代码
- 添加 《旧博客索引》（作为博客的第一篇文章）
- 添加 博客变更记录（本文）

### 2015.01 ~ 2016.12

很多折腾都记不清了，写个大概。

- 使用 Hexo 静态博客生成器 制作 独立博客
    - 通过网上常见的教程学会
- 尝试后，选用 Hexo Theme：Jacman
    - 根据当时的审美以及其组件的完备性作出选择
- Fork Jacman 后，看源码，修改博客的渲染效果
    - 顶栏、边栏、底栏、边距、配色、字体、Logo……
    - 文章显示更新日期、PV 量等……
- 自定义 Jack 博客主题组件
    - 热榜（PV Top N）
    - PV 文章阅读数（文章和主页文章流的显示）
    - UV 独立访客统计（在边栏）
    - 添加 一言：随机显示动漫名台词（在底栏）
    - 添加 博客秀、GitHub 秀、豆瓣秀（在边栏）
- PV 阅读数统计
    - 根据网上教程，通过 LeanCloud 的 API 实现
    - 修改统计策略：
        - 本地的测试环境下，不会增加 PV 计数
        - 增加 黑名单、白名单：文章 URL、域名
            - 是否增加计数？
            - 是否显示计数？
    - 热榜（PV Top N）
        - 根据统计数据，在边栏显示 Top N 的排名
- 404 页面处理
    - 在 404 页面下，通过 js 脚本控制，自动发布评论，记录错误的 URL 链接
        - 因为一些文章的路径修改后，外链引用出现错误
    - 跳转到 404 页面时，会自动更正链接，跳转到正确的页面去
        - 根据错误 URL 链接的统计，在 404 页面补充跳转规则，命中规则后，自动重定向到正确的 URL 上
- 评论
    - 启用 多说 的评论系统
    - 添加 Disqus，同时使用两个评论系统
    - 动态加载 Disqus：点击后加载
    - 添加 js 脚本片段，让访客自动为文章点赞（后来删掉了）
    - 添加 显示评论人的 IP 和 UA 信息
    - 定制化 评论模块的 CSS 显示效果
- 打赏
    - 添加 打赏模块（在边栏底部、每篇文章的底部）
    - 添加 支付宝 网页版打赏
    - 添加 PalPay 网页版打赏
    - 添加 支付宝、微信 二维码打赏
    - 定制 打赏文案 和 动效
- 自动化脚本（Windows 批处理脚本）
    - 可将 Evernote 中的笔记 导出为 HTML 格式的博客文章。
    - 可将 Evernote 中的笔记 导出为 MARKDOWN 格式的博客文章。
    - 可将 Evernote 笔记中的图片 自动导出并上传到图床，将文章中图片的本地链接替换为图床中的链接。
    - 集中处理 图片：压缩、自动上传、删除、修改（七牛云）。
    - 可一键 清理、重新生成网页，然后打开浏览器，显示网站主页。
    - 可一键 自动上传将网页部署到多个 GitHub Page 和 Gitcafe Page 等多个服务。
- 个人域名
    - 使用个人域名：icehe.me
    - 补充备用域名：icehe.gitcafe.io
    - 同时使用两个 Page 服务 icehe.me（指向 icehe.github.io） 和 icehe.gitcafe.io
    - 分流加速：使用 DNSPod 进行配置
        - 国外 IP 访问 icehe.github.io
        - 国内 IP 访问 icehe.gitcafe.io
    - 博客边栏显示主站和备用站
    - 分别给两个域名都添加了 Google Analytics、Google Webmaster、百度统计和百度站长工具
    - 由于 Gitcafe 被 Coding.net 收购，放弃了 icehe.gitcafe.io 的使用。
- 自动化 导入个人时间管理日志
    - 自动导出 自己在 Evernote 上做的 [时间管理日志](/lifelogs/)
        - 修改内容以适应 Hexo 的文章要求
    - 自动导入 成为 Hexo 文章，并部署到网站上
    - 后来改用更便捷的 App 进行管理时间，不再更新博客上的时间管理日志
- 改用 macOS 平台，重制所有相关脚本
    - 由 批处理脚本 改用 Shell、Python 和 AppleScript 等
- 改用 NexT 博客主题
    - fork 该项目后，重新根据 Jacman，迁移个人定制的功能
        - 例如「热榜 PV Top N」
    - 调整 CSS：边距、动效、字体、字号、配色
    - 调整 swig，定制化 首页的文章流的信息布局
    - 简化 分类
    - 去掉 标签 的显示
- FontAwesome 等图标字体变得常用
- 过程中对博客内容做过无数次重构
    - 例如「关于」页面（即现在的「简历」）、「导航」页面
    - Markdown 格式的文章中，为了提升内容的展示效果，直接混用了 HTML 标签
- ……

---

## 博客类型

- __静态博客 VS 动态博客__

### 更简单的方式

- 选择「去折腾」自己搭建个人博客真的有必要么？
    - 可能写写私人日记，跟好友聊聊天就足够了，连博客也没必要开。
- 如果要开，也可以选择已有的平台：
    - cnblogs 博客园、CSDN、SegmentFault、简书、知乎专栏 ……
- 优缺点：
    - 「可发现性」更强，节省了「被发现」的成本。
        - UGC（用户生产内容）平台对其内容，天生有自己的一套内容发现机制，如「发现」、「分类」、「最新文章」等。
        - 当然少不了推荐机制，只要内容做得足够好，平台也会主动来扩大你的内容的影响力，如「最热文章」、「推荐」等。
        - 不用特意做 SEO（优化搜索引擎的收录效果）。
            一个好平台会帮你做好相关的优化工作；
            如果平台的内容足够好，就算它的 SEO 优化做得不够，搜索引擎会主动适应它
            - 例如「知乎」就不算是 SEO 方面足够友好的站点，但是优秀内容足够多，有许多外链引用，百度就会千方百计去兼容它。
            - 所以，多做点外链宣传就好，加友链，在社交网络或各种社区的讨论区推广。
    - 可能你会嫌它们的「外观」丑、「定制性」不强，不能让每一个地方都能调整得符合你的心意。
        - 但有利就有弊，这是「便捷」的代价，你可以更专注于内容的生产，而非去折腾网站的细节。
- 也可以用 GitHub：
    - 将一个 __Project__ 作为个人博客的载体：因为 Web 端（浏览器）的 GitHub 项目代码页面能渲染显示 `*.md` 等 Markdown 格式的文件。
    - 将一个 Project 的 __Issues__ 作为载体：也支持 Markdown 语法的渲染显示，同时还兼具「评论」功能。
    - 将一本 __GitBook__ 作为载体，用写书的方式来写博客，也支持「评论」，可以算是静态博客的一种了。

### 特点

- __静态__ 指的是被请求的网页已经提早做好了，服务器直接将其发给浏览器即可。
- __动态__ 指的是被请求的网页需要服务器根据具体情况实时计算得出，生成完成后再发给浏览器。
- 区别在于：是否需要有在线的服务器去生成网页。

### 动态博客

- 运行的硬件环境 —— 服务器
    - 云服务器：现今通常的选择
        - 国内：阿里云、腾讯云、美团云…
        - 国外：AWS、Google、Linode…
    - 本地服务器：比较麻烦
        - 首先得拥有 __公网 IP__，才能被外界访问得到，然后对外提供服务。然而购买公网 IP 服务的费用，并不比购买一个拥有公网 IP 的云服务器便宜多少。
    - 要考虑服务器的「硬件配置」（处理能力）：带宽、流量、CPU、内存、存储空间 等……
- 运行的软件环境
    - HTTP 服务器: Nginx、Apache 等
    - 语言环境：PHP（PHP-FPM）…
    - 数据存储：MySQL、Redis …
    - …

### 静态博客

- 优点
    - __省钱__
        不用花钱购买服务器。
    - __省心（易上手）__
        不用配置、维护服务器，不用过多关心服务器的细节。
    - __安全__
        不需要过多关心服务器的安全问题，例如被入侵、D-DOS 等问题
    - __耐折腾__
        静态博客可以折腾的东西也很多，能够满足我折腾的欲望（见后文）。
    - __访问速度快__
        首先少了动态生成网页这个耗时的过程，而且还能挂载到多个 CDN 中，加速世界各地对这些网页的访问。
    - __服务稳定__
        只要确保生成好的页面没有问题，就能保证浏览器的展示效果，不会像动态博客服务器那样，可能由于软硬件环境导致动态生成的网页出错。只要挂载网站页面和资源的服务（器）还算靠谱，基本很难碰到服务器宕机的情况。
- 缺点
    - 少了亲身了解服务器各种细节、动手实践应用各种 Web 知识的机会，少学不少东西。
- 考虑
    - 我一开始 __图省事__，选择了静态博客。
    - 尝试搭建个人博客的新手，推荐从静态博客入门。
        - 由浅入深，门槛够低好入坑，以后还想要搭建动态博客也不迟。

### 静态博客生成器

- 静态博客生成器有不少，Top 4：
    - [__Jekyll__](https://jekyllrb.com/) GitHub 的官方推荐（Ruby）；
    - [__Hugo__](http://gohugo.io/) 基于 Go 语言，热门（Go）；
    - [__Hexo__](https://hexo.io/) 我的选择，基于 Node.js（JavaScript）；
        - 中国台湾的一个年轻人（大学时）编写的，中英文档齐全~
    - [__GitBook__](https://www.gitbook.com/) 用写书的方式来写博客；
    - 其它可参阅网站 [__StaticGen__](https://www.staticgen.com/) 。

### 挂载空间

- Page 服务的挂载方法，可见前文《[__搭建个人博客__](/web/build_blog/)》。
- 通常使用：
    - Page 服务：
        - [__GitHub Page__](https://pages.github.com/)
            - 全球通用，时不时会被国内封锁，不知道什么时候会全面封锁。
        - [__Coding Page__](https://coding.net/help/doc/pages/)
            - 相当于 GitHub Page 的国内版，来自 [Coding.net](https://coding.net/user) 的服务。
            - 在国内访问速度比较靠谱。
        - [__GitLab Page__](https://about.gitlab.com/features/pages/)
        - 还有其它代码托管服务商的 Page，请自行搜索。
    - CDN 服务：
        - 又拍云、七牛云等 CDN 服务商，可以提供静态网站的挂载和加速。
            - 但通常网站要先备案，才能提供服务，具体可见本文[「网站备案」](#网站备案) 小节。
    - 传统方式：
        - 用云服务器或本地服务器，配置好 Apache 或 nginx 等 HTTP 服务器，在浏览器请求页面时，将网页文件返回去。
            毕竟不是动态博客，基本没有必要这么做，浪费带宽、网费、电费等软硬件费用。

---

## 基础外观

### 博客主题

- 我选择的是 [__Hexo__](https://hexo.io/)，从官网的 [__Themes__](https://hexo.io/themes/) 页面中选择
- 我一开始用 [__Jacman__](https://github.com/IceHe/blog_theme_jacman)。
    - 扁平、简洁、美观；
    - 基础功能比较完备，包括基本的评论、分享、各种边栏组件等。
- 后来改用 [__NexT__](http://theme-next.iissnan.com/)。
    - 黑白扁平、很简洁、更美观；
        - 上述 Jacman 主题的作者 [WuChong](http://wuchong.me/) 现在也在用这个主题。
    - 基础功能非常完备，而且还在持续的优化维护中；
        之前不少需要我自己手动添加的第三方服务，都提供了详尽的支持。例如：
        - 文章的阅读量计数（PV）：基于 LeanCloud 来实现（以前靠自己看教程来添加）；
        - 网站的独立访客量（UV）：用不蒜子等第三方服务来统计（同上）。
- 选用一个基础功能完备、符合自己审美的博客主题，可以省很多功夫。
    - 可以自己做一个独一无二的个人专用 theme，但若是没有前端和设计的功底，恐怕效果不佳、费时费力还不好维护。
        - 当然经过一番折腾，能学到一些前端和设计的知识。
    - 一开始没有能力独立做一个靠谱的 theme，也可以在别人的 theme 的基础上，进行个性化的修改。
        - 我就 fork 了别人的 theme，定制了自己的模块和 CSS 效果（[链接](https://github.com/IceHe/hexo-theme-next)）。
        - 这样可以深入定制间距 `margin` `padding`、颜色、字体、字体样式，隐藏不想要的元素，增加新的功能模块……
        - 如果过程中做出了一些还不错的成果，也乐意分享的话，可以提 pull request 将它们回馈到 theme 的母项目中。
- 简述博客主题的制作：
    - 使用 __模板引擎__（或者说 模板库），配合静态博客生成器的 API，来生成博客的各种页面。
        - 例如：[__ejs__](http://ejs.co/)、[__swig__](https://github.com/paularmstrong/swig) 等
    - [Hexo Theme](https://hexo.io/docs/themes.html) 的简要制作说明。
        - 前人已经贡献了不少模板引擎以及相关的辅助工具到 [Hexo Plugins](https://hexo.io/plugins/) 了。
        - 可以看看各种 [Hexo Themes](https://hexo.io/themes/) 的效果。

### 文章内容

- Hexo 中的文章支持 Markdown 语法的渲染，也支持直接以 HTML 格式的发布的文章。
- 熟识 Markdown 各种语法。
    - 要多用，摸清它在 Hexo 及其 Theme 中的支持程度，及其显示效果。
- 有些效果 Markdown 支持不了，就直接用 HTML 标签来补。
    - 但是能用 Markdown 实现的，还是用 Markdown，简洁明了易于维护。
- 其实还有 Hexo 及其 Theme 支持的表现力更强的「标签」，例如：
    - Hexo「[标签插件](https://hexo.io/zh-cn/docs/tag-plugins.html)」
    - Hexo Theme NexT 的「[内置标签](http://theme-next.iissnan.com/tag-plugins.html)」；

### 字体

``` css
body {
    font-family: 'Lato', "PingFang SC", "Microsoft YaHei", sans-serif;
}
```
- 曾经有个妹子说，被我这个博客的字体吸引了，这个吸引人的字体就是 [__Lato__](http://www.latofonts.com/lato-free-fonts/)（西文字体）。
    - 可惜这个字体不是我主动选的，是 NexT 博客主题的默认设置的最优先使用的字体；
    - 第二优先使用的字体是 Apple 的字体「PingFang SC」苹方 简体中文版；
    - Windows 系统不默认安装以上字体，访问本站将用第三优先级的「YaHei」雅黑，效果不理想。
- 注意：
    - 字体资源需要额外加载时间，会影响网页的加载速度。
    - 通常使用 [Google Fonts](https://fonts.google.com/)，但是在国内被墙，严重拖慢加载速度。
- 优化：
    - 从更快速稳定的 CDN 中加载；
    - 国外用 Google Fonts，国内则优先使用墙内资源（自行搜索）；
    - 如果访客主要在墙内，全用墙内的资源也没差。

### 图标（字体）

- 「用字体来打包常用图标资源，以便加载和使用」。
    - 最常用 [__FontAwesome__](http://fontawesome.io/)，点击详见 [图标列表](http://fontawesome.io/icons/)。
        - 国内曾出现过 [__Font 屌__](http://lexrus.com/fontdiao/)，可惜作者已弃坑。
    - 用这种简便的方式引入图标资源，在必要的地方使用它们可以提高内容的表现力，吸引别人的注意。

#### FontAwesome 用法

- 1\. 先引用 FontAwesome 的静态资源。
    - 在 Chrome 浏览器访问本网页；
    - → 按快捷键 `⌘ ⌥ u` 查看本网页的源码；
    - → 按快捷键 `⌘ f` 查找；
    - → 输入 `awesome` 回车 `↩` 就可以找到以下这行引用。

    ``` html
    <link href="/lib/font-awesome/css/font-awesome.min.css?v=4.6.2" rel="stylesheet" type="text/css"/>`
    ```

- 2\. 在页面需要的地方插入以下 HTML 标签，即可显示 &nbsp;<i class="fa fa-heart"></i>
    - 在 Chrome 浏览器访问本网页；
    - → 右键点击上一行的心形图标；
    - → 在谈出菜单中，点击审查元素，即可看到以下这行引用。

    ``` html
    <i class="fa fa-heart"></i>
    ```

##### class 样式

- FontAwesome 还有其它一些 class 样式。
    - 维度众多：__宽度__、__大小__、__旋转__、__翻转__、__动态图标__、__图标列表显示__ 等，详见官网的 [__Examples 样例__](http://fontawesome.io/examples/)。
- __宽度__：给 HTML 标签的 class 添加 `fa-fw` 可以让这些图标以等宽的形式显示。
    <br/> 非等宽：<i class="fa fa-file"></i><i class="fa fa-bookmark"></i><i class="fa fa-bath"></i> &nbsp; 等宽：<i class="fa fa-fw fa-file"></i><i class="fa fa-fw fa-bookmark"></i><i class="fa fa-fw fa-bath"></i>
    ``` html
    <i class="fa fa-fw fa-file"></i>
    <i class="fa fa-fw fa-bookmark"></i>
    <i class="fa fa-fw fa-bath"></i>
    j``
- __大小__：大（ +33% ）`fa-lg`，以及两到五倍 `fa-2x` `fa-3x` `fa-4x` `fa-5x`
    <br/> <i class="fa fa-camera-retro"></i> &nbsp; <i class="fa fa-camera-retro fa-lg"></i> &nbsp; <i class="fa fa-camera-retro fa-2x"></i> &nbsp; <i class="fa fa-camera-retro fa-3x"></i> &nbsp; <i class="fa fa-camera-retro fa-4x"></i> &nbsp; <i class="fa fa-camera-retro fa-5x"></i>
    ``` html
    <i class="fa fa-camera-retro"></i>
    <i class="fa fa-camera-retro fa-lg"></i>
    <i class="fa fa-camera-retro fa-2x"></i>
    <i class="fa fa-camera-retro fa-3x"></i>
    <i class="fa fa-camera-retro fa-4x"></i>
    <i class="fa fa-camera-retro fa-5x"></i>
    ```
- __动态图标__：旋转 `fa-spin` ，跳动 `fa-pulse`
    <br/> <i class="fa fa-spinner fa-spin fa-3x fa-fw"></i> <i class="fa fa-circle-o-notch fa-spin fa-3x fa-fw"></i> <i class="fa fa-refresh fa-spin fa-3x fa-fw"></i> <i class="fa fa-cog fa-spin fa-3x fa-fw"></i> <i class="fa fa-spinner fa-pulse fa-3x fa-fw"></i>
    ``` html
    <i class="fa fa-spinner fa-spin fa-3x fa-fw"></i>
    <i class="fa fa-circle-o-notch fa-spin fa-3x fa-fw"></i>
    <i class="fa fa-refresh fa-spin fa-3x fa-fw"></i>
    <i class="fa fa-cog fa-spin fa-3x fa-fw"></i>
    <i class="fa fa-spinner fa-pulse fa-3x fa-fw"></i>
    ```

### 网站 logo

- 这里说的是 `favicon.ico`，在一个网站被访问或被收藏时，显示在该网站的浏览器标签页（tab）网页名称左边的那个小图标就是网站 logo 的 ico。
- 因为通常显示得比较小，所以最好选择一个比较简洁明了、有辨识度的图标。
- 如果选择的图片不是 ico 格式的，可以找一个工具网站，进行格式转换。

### CSS

- 即「[__级联样式表__](https://en.wikipedia.org/wiki/Cascading_Style_Sheets)」（[百度百科](http://baike.baidu.com/link?url=GXPKk5BXwHkL-armVUwEbCKisieAjr3xwFc9b6wfKV6SBcG-Q5WQ0SW09320tV5UfcvOSNSvNr5G6-GPvbu-ZK)）。
- 我的常用自定义样式：方便以 class 的方式，给网站模块和文章的页面元素添加样式。
    ``` css
    .bold   { font-weight: bold; }
    .center { text-align: center; }
    .hidden { display: none; }
    .no_underline { border-bottom: 0; }
    .white { color: white; }
    ```
- 例如：<span class="bold">加粗</span>
    ``` html
    <span class="bold">加粗</span>
    ```
    这里只是一种演示，能用就用 Markdown 的语法进行加粗：`__加粗的文本__` 或 `**加粗**`。
    ``` html
    <span class="bold hidden">隐藏元素</span>
    ```
    不用 `<!-- … -->` 是因为要同时修改两处。这里要隐藏直接给 class 加上 hidden，否则直接去掉就好了。

#### CSS 框架

- 我熟悉的有 [Less.js](http://lesscss.org/)、[stylus](http://stylus-lang.com/)（都是我用过的 Hexo Theme 中所依赖的）
    - 简洁、有序，降低 CSS 声明的冗余度，提高复用性。大大简化原始的 CSS 书写，提高编写效率。

### 配色

- 其实也是 CSS 配置的一环。
- 博客主题有自带的配色方案。
    - 如果不满意，可以看看网上的调色盘，不断尝试直到找到满意的配色；
    - 直接修改博客主题源码的 CSS 模板，重新生成页面，就可以查看效果。
- 即使有能力「审美」，不代表有能力「生产美」。
    - 建议还是找到一个靠谱的博客主题和靠谱的配色方案，不要自己调 RGB 找颜色，配色真的是一项学问。
    - 首先配色很浪费时间，即使一时找到满意的配色，通常也不耐看，一段时间后又要重新配。个人经验之谈……
    - 虽然折腾独立博客是一种乐趣，但我还是觉得花时间写好一篇文章更有价值。
    - 要搞清楚自己做独立博客的目的，折腾这些是不是对于你要专注的发展方向有助益？

### 主页信息流

- 常见内容：
    - 虽然有人定制这个页面：
        - 显示一张或几张相片；
        - 几个主要页面的链接；
        - 作品展示；
        - 各种动效、视频等。
    - 但博主还是希望别人关注自己的博客内容，所以通常还是用来显示文章流。
- 文章信息流
    - 文章显示形式：
        - 分页 不分页？
            - 可以直接取消文章流（只留文章的「归档」信息流）首页直接显示文章。
        - 显示 全文、摘要，还是用自定义的描述文本？
            - 摘要的截取方式：最初的段落？最初的几百字？特别指定的部分？
        - 显示 发布时间、更新时间？
            - 时间的 [展示格式](https://momentjs.com/docs/#/parsing/string-format/)
            - 是否显示更新时间，用 作者指定的时间 或 文章文件的修改时间（取自系统文件属性）？
        - 显示 文章配图?
            - 摘取文章内容中的图片，或是另外指定？
        - 显示 分类、标签？
            - 显示一个、多个还是全部？
        - 显示 PV 阅读数
            - 统计方式？LeanCloud，自建 API 服务，或其它第三方服务。
            - 显示格式：`10,233` `10.2k` `10k +` 等？
        - 显示 评论数？

### 顶栏

- 常见内容：
    - 网站 Logo
    - 网站名
    - 口号 Slogon
        - 箴言、座右铭？
    - 导航栏 nav
        - 包含到各个页面的链接：首页、分类、标签、归档、友链、留言板、关于、RSS 订阅、……
    - 搜索栏
    - 广告位
    - ……
- 显示形式：
    - 通常固定在页面顶部；
    - 一直浮动显示页面内容上方。

### 边栏

- 常见内容：
    - 导航
    - 分类
    - 标签
    - 友链
    - 留言板
    - 关于：个人、网站简介
    - RSS 订阅
    - 微信公众号 推广
    - 最近、热门、推荐
        - 文章
        - 评论
    - 社交网络展示
        就是以一个小方框模块来集中显示一些博主的社交网络信息
        - GitHub 动态
        - Douban 动态
        - 微博秀（动态）
    - 打赏
    - 广告位
    - ……
- 做法：
    - 其实不一定需要有边栏，比起啥都有（我认为杂乱无章）啥都想展示，还是有侧重点的展示比较好。
    - 不能只能考虑自己觉得爽，也要考虑访客爽才行，别人其实不一定想看到那么多东西，了解你那么多东西。

### 页脚

- 常见内容：
    - 版权声明
    - 作者名
    - 备案声明
    - 导航
        - 通常对应网页 head（顶栏）的导航
    - 「返回顶部」的链接
    - 箴言、座右铭
    - 社交网络的链接
    - 推荐文章
    - 友链
    - 杂七杂八……
- 不推荐加太多乱七八糟的东西，其实别人看到也不会点击查看。

## 拓展元素

### 「评论」系统

- 国外常用：
    - [__Disqus__](https://disqus.com/)
    - [__Facebook Comments Plugin__](https://developers.facebook.com/docs/plugins/comments/)
    - 其它自行搜索。
- 国内常用：
    - [__畅言__](https://changyan.kuaizhan.com/)（需要国内备案）
    - [__网易云跟帖__](https://gentie.163.com/)
    - ~~多说~~（盛极一时可是没盈利，已关闭，我只能从它完全迁移到了 Disqus）
- 以上多种系统 Hexo Theme [NexT 都默认支持](http://theme-next.iissnan.com/third-party-services.html)。
- 为了优化访问速度，我停掉 Disqus 的自动加载，只有你想看或写评论时，点击「加载评论」才去加载。
    - 毕竟 Disqus 的服务被墙了，加载它会严重超时，影响访问速度。

#### 延展特性

- 不同的评论系统，支持的特性可能有所区别，需要适当的取舍，或者同时支持多个评论系统：
    - __评论权限控制__
        - 需要登录注册？可能是第三方登录：
            国外的 Google、Facebook、Twitter 等
            国内的 QQ、微信、微博 等
        - 游客可评论？
            需要留邮箱、网站等联系方式？
        - 可匿名评论？
        - 评论审核？先审后显？可删改？
    - 评论支持「__楼中楼__」
        - 像是最常见的百度贴吧那种
        - 还是说，直接使用「复制需要引用的所有评论原文」的方式来实现的？
    - 带「__分享 Share__」按钮
        - 国内常用的社交网络和国外的还是有较大区别的，支持的平台可能有较大不同。
    - 带「__赞 Like__」按钮：
        - 可以对 这篇文章 或者 对某条评论 进行针对性的态度表达。
            - 例如还带。
        - 或者是其它「表态」：除赞之外的其它情感表达，例如「踩」vote down，还有高兴、悲伤、愤怒等。
    - 带「__评分 Rating__」
        - 一般都用 5 个星级来评分。
    - 评论可显示评论网友的 __IP 和 UA 信息__（操作系统、浏览器）？
        - 据说显示 macOS 的逼格比较高？（滑稽）
    - 是否显示头像，是否可__自定义头像__？
    - 可__订阅__该文章「__评论__」？
    - 可__推荐__博客的相关（其它）文章
    - 文章__数据统计__？PV 数、趋势等
    - 文章路径__变更__，评论可以修正依附的文章链接？
    - 评论的__导入导出__
        - 支持哪些其它厂商的评论系统服务（如无，可以使用相关的格式转换工具）
    - ……
- 尝试和感想
    - 关于「__评论__」
        - 尝试过让 __Disqus__ 和 __多说__ 同时加载，感觉加载太慢了，占地方不说，看起来还是有点怪。改成过自动加载 __多说__，__Disqus__ 要点击之后才加载。
        - 后来只用 __多说__，毕竟基本还是用中文写博客，没什么外国人看，更别说去评论了，所以还是只用国内的服务。
        - 最后 __多说__ 宣布停止运营，转投 Disqus。还得将评论数据导出，转换成 Disqus 兼容的格式后导入。
    - 关于「__赞__」按钮：
        - 我曾经加过一些很二的 js 脚本到网站中。例如，如果访客访问一篇文章，发现 ta 还没给它点过赞，就会自动点赞…… 这么做毫无意义，只是虚荣心作祟罢了。
    - 关于「__评分__」按钮：
        - 在朋友的博客发现了这个组件之后，本来一度很想给自己的博客也加上。心里挣扎了一番后，还是觉得博客简洁一点更好看。而且本来访客就很少，没必要做评分。

### 「分享」组件

- 博客系统 或者 博客主题 自带。
- 评论系统 通常也附带。
- 使用其它第三方组件，[__百度分享__](http://share.baidu.com/)（样式实在太丑），以及其它 js 的开源包，例如 [share.js](https://github.com/overtrue/share.js)。
- 根本就不去使用，毕竟我倾向于让网站简洁一些。
    - 如果内容够好，别人自然会复制你的文章链接然后分享出去。

### 友链

- 「友链」的意义？
    - 对我来说，是有交情的朋友的独立博客，我才会去加这个外链接。
    - 但更常见的理由还是：通过增加个人网站的「外链引用」来进行 SEO。
        - 所以才会在博客里看到许多关于「请求互相添加友链」的请求评论，即使他们互相不认识。
- 「友链」放哪里？
    - 首页边栏、底栏；
    - 特定的页面：
        通常链接会加到主页的导航栏中：
        - 「关于」页面；
        - 专门的「友链」页面；
        - 而我放到了博客的「[导航页](/bookmarks/)」中。

### __PV Top N 热榜__

- 有了文章 PV 的统计数据，自然就能通过查询 PV 前 N 名的文章，从而实现一个文章 PV 的热榜。
    - 「热榜」详见博客右边栏的「站点概览」或 [博客导航](/bookmarks/) 的第二节。
        - 可以用浏览器的「审查元素」去常看展示效果和实现代码，源码详见 Theme [NexT](http://theme-next.iissnan.com/) 。
    - 实现 PV 计数用的 LeanCloud，API 完备、文档清晰，定制化的查询很容易实现。
    - 除了 PV 计数，其实还可以做很多其它数据的统计和活用，可以开一下你的脑洞。
- 文章评论热榜的实现也是用类似的做法。

### __随机显示名言__

- [__一言__](http://hitokoto.us/index.html)
    - 随机显示动漫台词，可以加在 head 页头、footer 页脚、sidebar 边栏等地方。
        也是用其别人的 API 服务来实现的，不过现在已经去掉这个模块了。
    - 类似服务让我也想自己写一个出来，可以加上古今中外的古诗词、歌词、名台词、名言等。
        （暂时想到可以用 LeanCloud 的云服务来简单实现一个，有空有兴致再尝试）

### RSS 订阅

- 网上教程很多，在此不赘述。只提一个问题：
    - 网站内容混入了「[控制字符](https://zh.wikipedia.org/wiki/%E6%8E%A7%E5%88%B6%E5%AD%97%E7%AC%A6)」后，然后可能被收录到用于 RSS 订阅的文件中，如 `atom.xml`；
    - 通常这些文件以 UTF-8 的编码进行解码，控制字符导致其无法被正确解析，因而无法订阅。
- 网上的解决方法通常是：
    - 根据 Chrome 等浏览器读取错误的 `atom.xml` 这些 RSS 订阅文件时的报错信息，来了解混入了哪些控制字符，它们在哪里（哪些文件）；
    - 然后用文本编辑器搜索出它们，删掉即可。
- 但是！
    - 不是所有文本编辑器都支持「搜索控制字符」；
    - 即使支持，你知道如何输入这些控制字符吗？
    - 建议使用 Vim（亲测可用）、Emacs 来进行操作。
        - 用 Vim 打开包含控制字符的文件；
        - 在 NORMAL 模式下，输入 `/` 进入搜索模式；
        - 直接输入 `0x05`，然后回车，就能直接搜索到对应的控制字符；
            - 有些控制字符，可以通过先按前缀键 `^ v` 然后按控制字符的对应键来输入；
        - 通常这些控制字符都是没有作用的，删除之。
    - Vim 的目录搜索、批量替换等其它详细用法请自行搜索。

### 署名协议

- 比起开源项目的授权许可协议，文章的署名协议其实不用太纠结。
    - 要的就是「我把它用起来了」的优越感；
    - 虽然我写的东西不敢说有很大价值，最重要的还是以防万一，有个声明比较稳妥，便于维权。
- 我用的协议见文末。Hexo Theme NexT 提供了支持：
    - 只要在博客主题的 `_config.yml` 配置文件中开启 `post_copyright` 相关配置，就会自动在每篇文章下添加署名协议。

### 打赏

- 详见《[实现网站的打赏功能](/web/donate/)》
- Hexo Theme NexT 也自带了打赏模块，详见官方文章 [__开启打赏功能__](http://theme-next.iissnan.com/theme-settings.html#reward)。
    - 会自动在每篇文章末尾添加打赏用的二维码和文案。
    - 毕竟没几个人会打赏，为了精简网页元素，所以我只留了这一个入口 [__打赏博主__](/reward/)。

### 404 页面

- 就是访问到一个网站下的无效网页 URL 地址时，显示出来的页面。
    - HTTP Status Code（状态码）：404 NOT FOUND（找不到页面）。
- 比较流行的做法：
    - 接入「[__腾讯公益 404__](http://www.qq.com/404/)」
    - 其实什么都不做也没啥，反正你挂载网页用的服务商也有自己的 404 页面，可能不够有个性，但不会太难看。
        - 当然这样的话，如果网站是挂在个人域名下的，看 404 页面就能明显地看出你在哪里挂载的博客页面。
- 静态博客生成器，通常是在本地生成网页，浏览器访问本地网页查看效果，然后再将网页上传到互联网上。
    - 这么做 404 页面是不好测试的，简单的测试方法是：得将 `404.html` 等页面上传到你网站所在的互联网空间，才能看到效果。

#### 进阶做法

- 毕竟进阶做法，请自行检索实现方法，动手尝试，仅提供简单的思路。
- __自动反馈错误链接__
    - 就是「自动将访客访问到错误网页地址收集起来」。
    - 思路一、通常可以用 JavaScript 来先获取错误链接，然后调用 HTTP API（如 LeanCloud 等）来收集。
    - 思路二、开启网站的评论系统对匿名评论的支持，还是用 JavaScript 在 404 页面自动发表评论来反馈相关错误信息。
    - ……
    - 有了错误链接的数据，就可以进行下一步「错误链接重定向」了。
- __错误链接重定向__
    - 文章链接变更后，外链引用（包括搜索引擎的结果）没有及时更新或无法更新，需要 404 页面做处理，重定向正确的网页地址。
    - 因为刚开始用独立博客，没有考虑过页面 URL 的配置问题，以至于文章的发布的「年月日」成了文章页面 URL 路径的其中一部分。
        URL 不便于修改，而且比较长难记难输入，也不好看。
    - 实现方法：其实就是用原生 JavaScript 先获取错误的链接，匹配可能的旧链接，将网页重定向到对应的新链接、正确链接。

### npm

- 我选用的静态博客生成器 Hexo 基于 Node.js，必然用到 Node.js 的包管理器 [npm](https://www.npmjs.com/) 。
- 反正我觉得 npm 不是特别省心，升级 Hexo 或者相关插件时不时会出现一些恼人的错误。
    - 毕竟 npm 上的项目依赖通常比较多，版本号一日千里（夸张的说法），更新变动不少；
    - 有时不一定是用户的问题，也有可能是作者一不小心弄错了。
        - 例如，对应的依赖项目的版本有大更新，不兼容过去的版本，作者忘了锁住所需的依赖项目的版本号。
- 解决方法：
    - 最简单靠谱的方法：回退依赖项目的版本，即使用稳定的旧版本。
        - 需要修改 Hexo 博客源码根目录下的 `package.json` 手动声明指定依赖项目的版本号。
    - 上网搜索别人的经验，若无则等待，等他人修复好了提供教程。
    - 去对应的 GitHub 项目的 Issues 查看；若无自行创建一个，提醒作者修复。
    - 疑难杂症的粗暴解决方法：
        - Hexo 博客源码根目录下，`npm update` 更新依赖项目；
        - 不行的话，试试删掉 Hexo 博客源码根目录下的 `node_modules` 目录，重新 `npm install` ；
        - 不行的话，删掉系统用户的根目录下的 `node_modules` 目录，重新 `npm install -g` ；
        - 再不行，先更新一下系统软件（macOS 用 `Homebrew` 管理软件的话，用 `brew update` 和  `brew upgrade`），可能是需要 `Node.js` 及其相关的更新。

## 站长进阶

### 网站分析统计

- 国外常用 [Google Analytics](https://www.google.com/analytics/)。
    > Google Analytics（分析）不仅可以帮助您衡量销售与转化情况，而且能为您提供新鲜的深入信息，帮助您了解访问者如何使用您的网站，他们如何到达您的网站，以及您可以如何吸引他们不断回访。
- 国内常用 [百度统计](https://tongji.baidu.com/web/welcome/login)。
    > 百度统计是百度推出的一款免费的专业网站流量分析工具，能够告诉用户访客是如何找到并浏览用户的网站，在网站上做了些什么，有了这些信息，可以帮助用户改善访客在用户的网站上的使用体验，不断提升网站的投资回报率。
- 简而言之：分析访客，分析网站网页的价值。
    - 谷歌的服务由于被墙，在许多网络环境下加载 Google Analytics 所需的资源都会超时，严重拖慢了网站的访问速度，所以停止了对它的使用。
    - 特别对于我这个一文不名（$0）、纯属自嗨的独立博客来说，没必要进行那么多的分析。
        - 不过是想尝试使用网站分析统计服务，满足自己对它们的好奇心罢了。
    - 访客主要来自国内，留一个 __百度统计__ 即可。
        - 做了许多优化之后，现在本网站的网页基本实现了秒开。

### 站长工具

#### 搜索引擎收录

- 国外基本都用 [__Google Webmaster__](https://www.google.com/webmasters/#?modal_active=none)
    > - __您希望提高您的网站在网络上的曝光度？__我们可以助您一臂之力。您可以通过 Google Search Console 跟踪您的网站在搜索结果中的排名，并可以浏览更多网站站长资源。
    > - __为您的网站获取支持。__如果您的网站出现问题，您可以通过我们的常见问题列表、支持文档和测试工具快速获取帮助。
    > - __了解如何打造卓越的网站。__想要打造能够让用户畅享卓越体验并能在搜索结果中名列前茅的网站？请查看我们的课程和指南，了解如何打造用户可轻松找到的高品质网站。
- 国内常用 [__百度站长工具__](http://zhanzhang.baidu.com/site/)
    > 关键词影响力，是百度站长平台针对站点对于关键词数据分析的需求，推出的全新概念。
    > 涵盖该关键词下百度搜索可以为站点带来的全部收益指标，包括：排名、百度搜索流量、展现量等。
    > 在H5版本的站长平台工具中首发的关键词影响力工具检测数值有：整体影响力、最大影响力、站点影响力。
- 网站分析服务 和 站长工具 的用途是不一样的。
- 简而言之，__站长工具__ 对我们最重要的用途是：
    - 告诉搜索引擎我们的个人网站的存在，让它们去收录我们的个人网站的网页到它们的搜索结果中；
    - 然后查看实际的收录效果。
- 触发搜索引擎的收录行为的方法：（详情请见官方网站和文档）
    - 被动等待它们的爬虫来抓站；
    - 主动上站长工具，手动触发爬虫去抓站；
    - 主动提交站点地图 `sitemap.xml` 的地址，RSS 订阅用的 `atom.xml` 的地址也可以；
    - 还可以使用官方提供的 API，主动按需推送新上线的网页的地址和内容。

### 站内搜索

- 最简单的方式：
    - 设置一个搜索按钮，链接到以下地址后，访客再自行搜索：
        Google：__<https://www.google.com/?q=site:icehe.me>__
        百度：__<https://www.baidu.com/s?wd=site:icehe.me>__
    - 或者设置一个搜索框，将访客输入其中的 "关键词" 拼成以下 URL 地址，然后再跳转过去：
        Google：__<https://www.google.com/?q=site:icehe.me%20keyword>__
        百度：__<https://www.baidu.com/s?wd=site:icehe.me%20关键词>__
    - 本质是使用搜索引擎的语法：`[keyword] site:[site_url]`
        - 示例：`测试 site:icehe.me` [测试链接](https://www.google.com/?q=测试%20site:icehe.me)（然而跳转后还要按回车键才行……）
- Google 和 百度 都有提供专门的站内搜索功能，可是用起来还是不够方便。
    - 还是因为 Google.com 被墙，国内的非翻墙用户以上的方法都用不了。
    - 百度的站内搜索，体验不够好，被我放弃。
- 本地服务：
    - 比如 Hexo 的博客主题 [NexT](http://theme-next.iissnan.com/) 就自带了 [__Local Search__](http://theme-next.iissnan.com/third-party-services.html#local-search) 功能。
        - 本质是生成博客时，也根据博客的内容生成一个 `search.xml` 文件作为博客搜索的索引库，保存到线上；
        - 然后使用博客的 Local Search 搜索框时，Web 端（浏览器）的 js 脚本会根据 `search.xml` 文件执行检索操作。
        - 确实是一种很便捷、廉价的实现方式，我很喜欢，就用了这种方式。
- 其它搜索服务：
    - [__Algolia__](https://www.algolia.com/)、[__Swiftype__](https://swiftype.com/)、~~微搜索~~（国人作品，已废弃）
        - 体验都非常好。可免费使用一段时间，但终究要付费，好服务价格不菲！推荐土豪使用。
        - 否则试用期过后，虽然通常可继续使用，但功能受限：网站的索引不再持续更新，或者索引量上限很低。

### 网站域名

- 购买途径：
    - 国内域名运营商：例如，[__万网__](https://wanwang.aliyun.com/)。
        - 购买域名后，如需正常使用，首先要进行 "中国特色" 的「[__备案__](http://baike.baidu.com/item/%E7%BD%91%E7%AB%99%E5%A4%87%E6%A1%88)」
            - 将域名实名绑定到特定的自然人或法人，以便「追责」。
    - 国外域名运营商：[__NameCheap__](https://www.namecheap.com/)、[__GoDaddy__](https://www.godaddy.com/)，域名比价网站 [__domcomp__](https://www.domcomp.com/) 。
        - 无需备案，也无法备案。需要将域名转到国内网站接入商，才能进行备案。
            - 等于将网站域名（接入服务）绑定到服务商，以便随时「拔掉你网站服务器的网线」。

#### 网站备案

- 为什么我没有备案？（答案并不敏感和复杂）
    `（六）安装备案电子标识：网站所有者应于 15 日内将备案电子标识安装在网站首页的右下方……`
    - 这个备案标识实在太丑了，我不愿意放……
- 没备案的麻烦：国内的许多针对网站站长的服务，要求你的网站备案了才能使用。例如：
    - 「畅言」的评论系统；
    - 网站挂载到 CDN 进行加速访问（「七牛云」等）；
    - 不将域名绑定到微信公众号，就无法保证你的网站在微信内顺畅地访问：
        - 被转码、拦截，正常的 js 脚本也被阻止运行，跳转很麻烦甚至无法跳转等。

### 域名的 DNS 解析

- 我用国内的免费版的 [__DNSPod__](https://www.dnspod.cn/) 服务就够了。
- 当然，你在哪购买的域名（我用了 NameCheap），可以尝试用那个域名销售商的 DNS 服务。
    - 如果你选的 DNS 服务是国外的，在国内，你域名的 DNS 查询稳定性和速度可能不理想，所以我还是使用国内的服务。
    - 不靠谱的服务商会可能会让 DNS 查询比较花时间，我不希望这成为个人网站访问速度的瓶颈。

### 图床 与 图片

- 最简单的方法：
    - 直接把图片放在挂载网站的空间中，例如 GitHub Page 的项目。
        - 虽然每个 GitHub 账户在不付费的情况下，有一定储存容量上限，但一般够用。
        - 稍微不够用，可以多申请几个 GitHub 帐号来缓缓。
        - 如果图片太多还是使用第三方的图床服务比较靠谱。
- 图床服务商：
    - 又拍云：服务很好，但对于一文不名的独立博客来说费用太贵；
    - 七牛云：服务不错，免费 10 GB 空间，够用；
    - 微博：…… 其实就是你用微博发图片，然后使用图片引用链接而已。
    - ……
- 图片压缩：
    - 虽然图床空间一般够用，下载速度也不差，但要是图片太大也是会影响的网页的加载速度的。
    - 所以，首先确保网站页面在常用的网页浏览设备的显示效果良好，然后多余的像素、占用的比特空间可以都压缩掉。
- 图片压缩方法：
    - 上传前压缩：
        - 可以是命名行指令和脚本；
        - 或者是专用的带 GUI 的 Apps。
    - 长传后压缩：
        - 或者图床空间自带压缩效果……
            - 床服务的上传服务的 API 带压缩的选项。

### 访问速度优化

- Chrome 浏览器自带的开发者工具，就自带网络资源加载和网页性能的分析工具。
- 如果使用 Google 和 百度 的网站分析统计工具 或 站长工具，里面也有优化分析工具，给你提供建议。
- 其它可以上网搜索相关的内容。性能优化这条道路无穷无尽，我也走过弯路，做过许多无用功……
    - 其实在大多数地方达到「秒开」（1~2 sec）就够了，没必要追求太机制的体验。
    - 但是要是囿于某些资源，页面能看全了，但「菊花」（刷新标识）还是转个不停，这就感觉很不好了。
- 为了优化访问速度，我主要做了：
    - Google Analytics 只留「百度统计」；
    - 停掉 Disqus 的自动加载，只有你想看或写评论时，点击「加载评论」才去加载；
    - 字体、图片、js 库，优先用国内的 CDN 资源，否则放国内图床（七牛云），再不济就放 Coding Page 的博客源码项目里。

### 网站结构

- 我的思路
    - 所有页面即文章（POST），包括「关于」页面这种，除了 404 页面。
        - 会在首页文章流显示的是 POST 类型文章的链接；
        - 不在首页文章流显示的是 PAGE 类型的页面；
        - 首页是 INDEX 类型的页面。
    - 尽量不使用 PAGE 类型的页面，除非是打算不暴露外链的隐藏文章，哈。

### 自动化的尝试

#### Evernote 笔记导出为 Hexo 文章

- 文章导出为 HTML，挪到博客源码的文章目录下；
- 其中的图片资源，先经过脚本工具压缩，再上传图床，计算得出其网络路径；
- 网页的 HTML 文件，会经过一番修改：
    - 补充一些 Hexo 生成文章页面需要的元标签；
    - 将其中图片的本地路径，替换为网络路径。
- 参考代码：
    - [Python_for_Day_Log](https://github.com/IceHe/Python_for_Day_Log)
    - [AppleScript_for_Evernote](https://github.com/IceHe/AppleScript_for_Evernote)
    - [AppleScript_for_me](https://github.com/IceHe/AppleScript_for_me)
    - [my_scripts_on_win](https://github.com/IceHe/my_scripts_on_win)
- 当然，其它一些笔记软件可以导出为 Markdown 格式的文件就更好弄了。
    - 注意它们支持的可能是自定义过拓展过的 Markdown 语法，Hexo 或你的 Hexo Theme 不一定支持。
    - 所以 Markdown 标签可能也需要经过一定的替换等处理（考验你的正则表达式），然后做好测试，检查实际显示效果（难免百密一疏）。

#### 其它经验

- 关于 Evernote
    - 用脚本在 macOS 导出 Evernote 的笔记，可以用 AppleScript；
        - 但其命令行的 API 不如 Windows 上的好，Evernote 有专门的 `*.exe` 的支持批处理或 Power Shell 的脚本调用。
    - 以前文章导出为 Evernote 的专用笔记格式 `.enex` 时，图片以 BASE64 的格式存储，还要先转码后保存成单独的文件进行处理；
    - `.enex` 中的文章正文，基本符合 HTML 的标准；
    - `.enex` 格式中有一些 Evernote 专用的标签，保存版本号、图片引用、文章名、分类、标签、笔记本名等。
- 重复的工作
    - 有些不会长久使用的自动化操作，还是手动来做更快，写脚本维护成本确实非常高，并不省心，只是觉得用得爽有成就感。
        - 根本在于这些脚本的没有「放大效应」「规模效应」，可能只有你自己一个人用，所以没能成规模地节省很多人的时间。
    - 当然最后还是要说一句，折腾自动化还是挺有成就感的。
        - 虽然可能没什么人在意，找工作时面试官也不会在意。
        - 吐槽：效率软件的使用，面试官通常也不看重，我泪目，我承认有一定道理，但是不服…… 至少我搬砖比一般人快多了。