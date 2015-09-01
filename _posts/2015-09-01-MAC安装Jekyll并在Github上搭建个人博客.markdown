---
layout: post
title:  "MAC安装Jekyll并在Github上搭建个人博客"
date:   2015-09-01 21:17:58
categories: jekyll update
---

1.如果是墙内用户的话建议将ruby的源切换到[RubyGems 镜像 - 淘宝网][ruby-taobao].
{% highlight ruby %}
gem sources --remove https://rubygems.org/
gem sources -a https://ruby.taobao.org/
gem sources -l
#####确保只有 ruby.taobao.org
gem install rails
{% endhighlight %}

2.安装 jekyll
{% highlight ruby %}
gem update --system
gem install jekyll
#####如果使用的标记语言是Markdown，则需要另外安装
gem install rdiscount
#####如果使用的标记语言是Textile,则需要另外安装
gem install RedCloth
{% endhighlight %}

3.创建jeklly项目并上传至Github
{% highlight ruby %}
mkdir 'you project name'
jekyll  new 'you project name'
cd 'you project name'
git init
{% endhighlight %}


[Jeklly官网介绍][project-pages]上说要部署在github上必须名称叫gh-pages，所以需要创建一个gh-pages的分支
{% highlight ruby %}
git checkout --orphan gh-pages
git add .
git commit -a -m "v0.1"
{% endhighlight %}


上传到github
{% highlight ruby %}
git remote add origin https://github.com/(github username)/(you project name).git
git push origin gh-pages
{% endhighlight %}


到此处就可以访问你在Github上的blog啦

4.修改后提交
{% highlight ruby %}

{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[project-pages]:      http://jekyllrb.com/docs/github-pages/#project-pages
[ruby-taobao]:   http://ruby.taobao.org/