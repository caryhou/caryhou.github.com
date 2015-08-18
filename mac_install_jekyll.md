---
layout: page
title: OS X
permalink: /mac/
---
# MAC安装Jekyll并在Github上搭建个人博客

#### 1.如果是墙内用户的话建议将ruby的源切换到[RubyGems 镜像 - 淘宝网].
    gem sources --remove https://rubygems.org/
    gem sources -a https://ruby.taobao.org/
    gem sources -l
    #####确保只有 ruby.taobao.org
    gem install rails
#### 2.安装 jekyll 
    gem update --system
    gem install jekyll
    #####如果使用的标记语言是Markdown，则需要另外安装
    gem install rdiscount
    #####如果使用的标记语言是Textile,则需要另外安装
    gem install RedCloth
#### 3.创建jeklly项目并上传至Github
    mkdir 'you project name'
    jekyll  new 'you project name'
    cd 'you project name'
    git init
#####[Jeklly官网介绍]上说要部署在github上必须名称叫gh-pages，所以需要创建一个gh-pages的分支
    git checkout --orphan gh-pages
    git add .
    git commit -a -m "v0.1"
#####上传到github
    git remote add origin https://github.com/(github username)/(you project name).git
    git push origin gh-pages
#####到此处就可以访问你在Github上的blog啦

#### 4.修改后提交
    添加所有新增文件
    git add .
    提交所有修改
    git commit -a -m "注释"
    将修改提交到Github上
    git push origin gh-pages