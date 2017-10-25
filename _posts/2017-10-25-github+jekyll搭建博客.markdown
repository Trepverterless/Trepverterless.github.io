---
layout: post
title: Jekyll 搭建 github 博客
date: 2017-5-30 0:0:0 +0800
categories: technology
tags: jekyll github 博客
img: https://ooo.0o0.ooo/2017/05/30/592d41ed710a5.jpg
---
jikell+github免费搭建个人博客

* 
{:toc}

#申请github账号  
##关于GitHub
1. github pages有300M免费空间；
2. 学着用github，享受github的便利，上面有很多大牛，眼界会开阔很多；
3. 可以绑定自己的域名；
4. 无需自己搭建服务器；
5. github是趋势；
##步骤
 - 首先登陆[github](http://github.com "github")
 - 根据提示注册账号
 - 点开个人的github主页，新建一个仓库（repositories)
 - 新建仓库名为[name].github.io
 - 进入新建仓库，点击设置（setting)，找到github pages进行设置
 - 可以直接选择他推荐的模板（choose a theme),但是个人觉得那些模板一点都不酷炫
#创建一个酷炫的个人博客
如果不想，那么就不用往下看了
##关于不同的博客模板介绍（大佬请自动忽略）

###jikell

jekyll是一个简单的免费的Blog生成工具，类似WordPress。但是和WordPress又有很大的不同，原因是jekyll只是一个生成静态网页的工具，不需要数据库支持。但是可以配合第三方服务,例如Disqus。最关键的是jekyll可以免费部署在Github上，而且可以绑定自己的域名。

###wordpress

WordPress是使用PHP语言开发的博客平台，用户可以在支持PHP和MySQL数据库的服务器上架设属于自己的网站。也可以把 WordPress当作一个内容管理系统（CMS）来使用。
WordPress是一款个人博客系统，并逐步演化成一款内容管理系统软件，它是使用PHP语言和MySQL数据库开发的。用户可以在支持 PHP 和 MySQL数据库的服务器上使用自己的博客。
WordPress有许多第三方开发的免费模板，安装方式简单易用。不过要做一个自己的模板，则需要你有一定的专业知识。比如你至少要懂的标准通用标记语言下的一个应用HTML代码、CSS、PHP等相关知识。
WordPress官方支持中文版，同时有爱好者开发的第三方中文语言包，如wopus中文语言包。WordPress拥有成千上万个各式插件和不计其数的主题模板样式。

###hexo

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

##jekyll搭建个人博客

因为github很好的支持jekyll所以本文就介绍github搭建（反正扒的模板，都差不多=v=)

 - 查找喜欢的模板(可以在[jekyll theme](http://jekyllthemes.org/)查找）
 - downlode或者查看他的github点击fork到自己的仓库里通过改为[name].github.io直接使用（但是fork下来不建议自己使用,可以先fork然后download到本地，让后上传到自己的[name].github.io仓库里）
 - 这样就把别人的博客复制为自己的博客了，但是和别人的博客一模一样，要想真正的变成自己的博客还要更改配置文件  
 这里要介绍jekyll的目录结构  ：

　　├── index.html  
　　├── _config.yml  
　　├── assets  
　　│　　├── blog-images  
　　│　　├── css  
　　├── fonts  
　　│　　├── images  
　　│　　└── javascripts  
　　├── _includes    
　　├── _layouts  
　　├── _plugins  
　　├── _posts  
　　└── _site  
其中＿config.yml里就可以配置个人博客信息，把name，title之类的已改就变成自己的了（=v=)

 - 然后把自己要写的文章用markdown写来放在_posts文件下就ok啦
 