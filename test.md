---

layout: post
title: 初识 jekyll
categories: Blog
description: jekyll 的学习经历
keywords: 2017, jekyll
comments: true

---

新建了一个 GitHub Pages, 其实之前很早就接触到了,只不过没有坚持的做下来，做了一个半成品，现在终于有时间把这个博客给搞起来了,
以下是我做这个项目的时候遇到的问题和总结的一些经验

## 一、Github Pages 是什么


github Pages 可以被认为是用户编写的，托管在github上的静态网页。github提供模板，允许站内生成网页，但也允许用户自己编写网页，然后上传。这种上传并不是单纯的上传，而是经过 Jekyll 程序的再处理的。

## 二、Jekyll 是什么？

Jekyll 是一个静态站点生成器，它会根据网页源码生成静态文件。它提供了模板、变量。插件等功能，所以实际上可以用来编写整个网站。整个过程是这样的，你现在本地编写符合Jekyll 规范的网站源码，然后上传到
github，然后由github生成和托管整个网站。

这样做的好处：
    
    * 免费，无线流量
    * 享受git的版本管理功能，不用担心文章遗失
    
## 三、搭建项目

###### 1. 创建项目

github 的站点分为两种站点：
    
    1. 用户和组织的站点
    2. 项目的站点

用户和组织的站点: 用户和组织的站点被放置在一个特殊的专用仓库中，在该仓库中只存在Github Pages 的相关文件。这个仓库应该根据用户/ 组织的名称来命令，其实就是你的github用户名，例如：@marksjin 的用户站点仓库应该被命名为 marksjin.github.io，这个也是你的最后生成网站首页的地址 https://marksjin.github.io/，该仓库中的master分支里的文件将会被用来生成这个站点，所以你要保证你的文件存储在master上。

项目的站点: 但是另一种情况比较特殊，这种叫做项目的站点，不通于用户和组织的站点，项目的站点文件要放在项目本身仓库的gh-pages 分支中，才能被Jekyll处理，生成的站点才能部署到你用户站点的子目录上，例如：你新创建了一个me的项目，你想要将该项目放在你的Github Pages上，那么你就应该把项目的内容放在 gh-pages分支上，这样生成的地址为 https://marksjin.github.io/me（注意：如果此时你的用户站点也有一个对应 https://marksjin.github.io/me 的地址，那么此时会以你新建项目的内容为准，会覆盖掉在用户站点上所写的内容）。

我们现在建设一个用户和组织的站点：

    * 进入[Github Pages](https://pages.github.com/) 网站，依次选择Project site、Start fron scratch、create a new respository，项目的名字要写成 username.github.io（切记）
    *创建完之后在本地clone 下来项目
    *在项目跟目录下，简历一个名为_config.yml 的文件文本。它是jekyll的设置文件，我们要在这里填写如下的内容，其他的可以参考[官方网站](http://jekyllrb.com/docs/configuration/) [中文版网站](http://jekyllcn.com/docs/configuration/)
