---
layout: post
title: 'learning hbase'
tags: [hbase]
categories:
- learning
---

###数据模型
####面向列的存储
####变化个数的列

###架构
![hbase architecture]({{BASE_PATH}}/assets/img/hbase-arch.png)

####水平扩展
####读写流程
####HMaster HA
HMaster的主要职责region balancer, regionserver的failover，表的管理操作等。
HMaster不参与正常的数据读写流程，因此Hmaster短暂的不可用不会影响hbase的可用性。

HMaster没不存储任何关键信息, hbase路由信息存储在ROOT和META表里面，
表的描述消息存储在分布式文件系统里面， RegionServer/Region状态消息存储在zk上

当主hmaster异常推出时候，
同过zk抢锁/hbase/master的锁，backup的HMaster升级为主，执行Hmaster的控制功能。

因此hmaster不是hbase里面的单点。

####Regin拆分

####原子性
主要支持row级别的原子性，不支持跨行，跨表的原子性，但支持单个region内部跨row的原子性。
####一致性
强一致性. 写成功之后，所有的client都可以马上读到最新的数据。
####持久性

###高级特性
####二级索引
因为hbase现在还不支持跨行扩表的原子性，所以在hbase还不支持强一致的全局二级索引。
可以利用hbase region内部跨row的原子性来实现强一致的局部二级索引。
对于很多数据以用户为中心的互联网产品数据，通过设置region拆分策略(), 保证一个用户的数据一定落在一个region上，不会跨region。
这样对这个用户跨row的操作就可以保证强一致性。
####mapreduce支持
hbase扩展hadoop mapreduce的输入输出流，使得mapreduce作业可以非常方便的直接读写hbase。
####Coproccsor

###部署
####测试环境
minicluster. standalone
####生产环境
生产环境部署，hadoop依赖hdfs作为分布式文件系统，作为数据的持久化存储，依赖zookeeper提高的分布式锁等服务。在系统层面上， 
还依赖系统ntp服务保证regionserver之间的时钟同步（很多hdfs/hbase依赖租约协议）。

####异步跨机房备份
![hbase replication]({{ site.url }}/assets/img/hbase-replication.png)
####安全&权限
hadoop/hbase在kerberos认证基础上实现列级别的权限管理，能够保证数据安全，防止非法用户访问。

###hbase社区

###劣势
- hbase构建在hadoop，zookeeper之上，实际部署会遇到很多问题，对于中小的创业公司无法很快掌握这么庞大的系统。cloudera
- hbase
