# springcloud_config
springcloud自带分布式配置中心Config Server Demo

# 分布式配置中心项目模型：

1、git远端存储持久配置文件；

2、springcloud config server 从git上拉取文件缓存在本地服务器；

3、微服务项目（作为config client端）使用配置文件的时候，从本地configServer上拉取。

# 配置文件如何实时刷新！
配置文件在git上的更改默认无法刷新config client配置，做到刷新客户端有两种方式：

1、手动刷新（推荐使用） --- 需要人工调用接口，读取最新配置文件（监控中心接口）；每次人工修改完配置文件后，client端采用post方式人工调用/actuator/refresh进行刷新；

2、自动刷新（不推荐使用） --- 消息总线进行时事通知 -----springBus （后期再讲），springboot对每个服务会创建监听，这样影响服务性能

本项目中的分布式演示springcloud自带的分布式配置中心Config 的功能；配置文件存在gitee仓库cloud_itmayi_config中的zkconfig文件夹中;
仓库地址:https://gitee.com/wx_public/cloud_itmayi_config.git


