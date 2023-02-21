# 工程简介
在业务逻辑的异步处理，系统解耦，分布式通信以及控制高并发的场景下，消息队列有着广泛的应用。本项目基于Spring的AMQP模块，整合流行的开源消息队列中间件rabbitMQ,实现一个向rabbitMQ添加和读取消息的功能。并比较了两种模式：生产者-消费者模式和发布-订阅模式的区别。AMQP作为比JMS更加高级的消息协议，支持更多的消息路由和消息模式。


# 延伸阅读

包含的特性如下：

 输入图片说明

如上图，生产者消费者模型：添加了一个队列，并创建了两个消费者用于监听队列消息，我们发现，当有消息到达时，两个消费者会交替收到消息。这一过程虽然不用创建交换机，但会使用默认的交换机，并用默认的直连（default-direct）策略连接队列；
输入图片说明

如下图，发布订阅模型，添加两个队列，分别各用一个消费者监听，设置一个交换机，类型为广播（fanout），交换机会将收到的消息广播给所有相连的队列：
输入图片说明 输入图片说明 输入图片说明

direct直连交换机通信模型，包括一个direct交换机，三个binding，两个队列，两个消费者监听器，消息只会被投入到routingkey一致的队列中
输入图片说明 输入图片说明

4.topic主题交换机通信，包括一个topic交换机，三个binding，两个队列，两个消费者监听器，消息只会被投入到routingkey能够匹配的队列中，#表示0个或若干个关键字，*表示一个关键字

输入图片说明 输入图片说明

附录：中央技术储备仓库（Central Technique Reserve Repository）
基础篇:职业化，从做好OA系统开始
Spring boot整合Mybatis实现增删改查（支持多数据源）输入图片说明
Spring,SpringMVC和Hibernate的整合实现增删改查
Spring boot整合activiti工作流引擎实现OA开发输入图片说明
Ruoyi-boot集成工作流引擎Flowable实例输入图片说明
Spring发布与调用REST风格的WebService
Spring boot整合Axis调用SOAP风格的web服务
Spring boot整合Apache Shiro实现RBAC权限控制
使用Spring security实现RBAC权限控制
中级篇：中间件的各种姿势
Spring boot整合mongoDB文档数据库实现增删改查
Spring连接Redis实现缓存
Spring连接图存数据库Neo4j实现增删改查
Spring boot整合列存数据库hbase实现增删改查
Spring平台整合消息队列ActiveMQ实现发布订阅、生产者消费者模型（JMS）
Spring boot整合消息队列RabbitMQ实现四种消息模式（AMQP）
23种设计模式，源码、注释、使用场景
使用ETL工具Kettle的实例
Git指南和分支管理策略
使用数据仓库进行OLAP数据分析（Mysql+Kettle+Zeppelin）
高级篇：分布式系统和大数据开发
zookeeper原理、架构、使用场景和可视化


