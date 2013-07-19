---
layout: post
category : toolchains
tags : [saltstack]
---
{% include JB/setup %}


### 安装
参考：<http://wiki.saltstack.cn/reproduction/om-auto-salt#salt.2BdoRbiYjF->

#### 服务端
    yum install salt-master

启动

    /etc/init.d/salt-master start

####客户端
  
    yum install salt-minion -y

修改配置文件:/etc/salt/minion

启动：

    /etc/init.d/salt-minion start

master端接受key：

    salt-key -A

重启

    /etc/init.d/salt-minion start

###用例

###问题

