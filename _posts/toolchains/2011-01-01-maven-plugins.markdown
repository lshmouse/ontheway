---
author: lshmouse
date: 2011-01-01 01:01:01+00:00
layout: post
slug: maven-plugins
title: 好的Maven2插件推荐
category : toolchains
tags : [maven, jetty]
---

### Maven Jetty Plugin

开发在eclipse开发web服务，测试比较麻烦，例如以前使用resin启动服务，除了配置，还需要copy工程，更大的问题在于，你修改了java了，需要重新打包发布，然后重新启动resin。使用这个插件可以减少你的工作量，他使用轻量级的jetty作为web服务器，只需要在工程下输入：maven jetty：run 他就会自动帮你部署启动服务，并且他可以检测java类的变化，自动重启服务，帮你减少很多工作量。对于web开发者来说，你一定会喜欢上这个插件的。详情和配置参见：[http://docs.codehaus.org/display/JETTY/Maven+Jetty+Plugin](http://docs.codehaus.org/display/JETTY/Maven+Jetty+Plugin)

### Maven Dependency Plugin

maven工程依赖分析插件，能后很好分析工程依赖问题，主要解决依赖冲突问题，这个复杂工程里面非常头痛的问题。这个插件包含很多命令，可以帮你避免依赖问题，值得一试。

详情和配置参见：<http://maven.apache.org/plugins/maven-dependency-plugin/>


### Maven Compiler Plugin

maven 编译插件，设置编译参数，打包配置等，非常有用。详情和配置参见：<http://maven.apache.org/plugins/maven-compiler-plugin/>

