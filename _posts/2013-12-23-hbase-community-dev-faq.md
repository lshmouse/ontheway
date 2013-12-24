---
layout: post
title: "HBase Community Dev FAQ"
description: ""
category: HBase 
tags: [HBase]
---
{% include JB/setup %}

###HBase发布包编译

对于Hbase 0.94, 执行mvn命令：
	
	mvn clean package -Pdist -Dtar

生成的发布包在： target/hbase-0.94.x-SNAPSHOT.tar.gz

对于HBase 0.96以上版本使用：

	mvn -DskipTests -Phadoop-2.0 clean package assembly:single
生成的发布包在：
	hbase-assembly/target/hbase-0.97.0-SNAPSHOT-bin.tar.gz

### Hbase转git开发
####下载hbase trunk:
	
	git clone git://git.apache.org/hbase.git

####0.94分支： 
	
	git branch hbase-0.94 remotes/origin/0.94

####0.89-fb 分支
	
	git branch 0.89-fb remotes/origin/0.89-fb

生成patch 
 
	git diff --no-prefix  > HBASE_XXXX.patch

###社区reviewboard使用
地址: https://reviews.apache.org
注意使用svn提交到0.94分支时候，Base Directory: 需要填写
 ../branches/0.94

###HBase trunk 重新生成pb
在hbase-protocol执行, 注意本地的protoc版本需要和pom里面版本保持一致
	
	mvn clean package -Pcompile-protobuf

###jira高级搜索

jira的高级搜索支持一些高级语法.
例如搜索提交的所有issue： 
	
	reporter = currentUser() ORDER BY createdDate Desc

参见文档：https://confluence.atlassian.com/display/JIRA061/Advanced+Searching
