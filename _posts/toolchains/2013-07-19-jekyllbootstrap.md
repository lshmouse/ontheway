---
layout: post
category : toolchains
tags : [jekyll, bootstrap]
---
{% include JB/setup %}

###安装

    git clone https://github.com/plusjade/jekyll-bootstrap.git PROJECT

###本地调试
安装jekyll: 

    sudo apt-get install rubygem
    sudo gem install jekyll
在jekyllbootstrap项目目录启动： 

    jekyll serve

see: <http://localhost:4000/>

###github 发布
申请一个git项目: PROJECT

    $ git remote set-url origin git@github.com:USERNAME/PROJECT.git
    $ git push origin master
查看: <http://USERNAME.github.com/PROJECT>

###去掉discover
参考：<http://www.v2ex.com/t/49949>

申请一下

###MarkDown 语法参考
<http://wowubuntu.com/markdown/>

###参考
-<http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html>
-<http://jekyllbootstrap.com/usage/jekyll-quick-start.html>
