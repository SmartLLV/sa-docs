---
layout: default
title: 逻辑架构到应用程序映射指南
---

# 1.逻辑架构
逻辑架构由三层模型（表示层、业务层、持久化层）构成

{:.no_toc}

* 目录
{:toc}

## 1.1.表示层
- 顾客端使用 移动端Web 作为表示层，提供用户点餐子系统、用户订单子系统
- 餐厅端使用 Web 作为表示层，提供餐厅信息管理子系统、菜品管理系统、二维码管理系统、订单管理子系统、审计子系统

## 1.2.业务层
服务器充当业务层的角色，为表示层的各个子系统提供相应的服务模块

## 1.3.持久化层
- MongoDB 提供了数据的持久化服务
- Redis 提供了会话的持久化服务

# 2.框架目录设计
## 2.1. 前端
```
─ src
 ├── common                         #
 │  ├── audio                       #音频
 │  ├── images                      #图片
 │  ├── javascript                  #api接口、cache、config等js文件
 │  ├── style                       #公用style
 ├── components                     #组件
 ├── pages                          #页面，处理业务，主要分为三个模块
 │  ├── admin
 │  ├── seller
 │  ├── user
 │  ├── index.vue
 │  ├── login.vue
 ├── router                         #路由
 │  ├── index.js
 ├── store                          #vuex的store，分了三个模块
 │  ├── admin
 │  ├── seller
 │  ├── user
 │  ├── index.js
 ├── App.vue
 ├── main.js
```

## 2.2.后端
```
─.
 ├── app
 ├── ├── common            # 工具
 ├── ├── controllers       # 业务
 ├── ├── models            # 定义数据库模型
 ├── db_vue                # 导出来的数据库数据
 ├── public                # 前端资源
 ├── routes                # 路由
 ├── app.js
 ├── config.js             # 短信api的key相关
```

# 3.与 ECB 关系
ECB中：
- Entity：代表系统数据，如：订单、餐厅、菜品等
- Boundary：与用户的接口，如：界面、网关、代理等
- Controller：在 Boundary 和 Entity 中衔接的媒介，编排来自 Boundary 的命令的执行

在本系统中，Boundary有三个部分：
- 顾客端小程序用户界面
- 餐厅端 Web 程序用户界面
- 服务端 Nginx 反向代理服务器

Controller 包含：
- 服务器框架目录设计中，`controller` 目录下定义了所有的相关内容，它们接收来自上述 Boundary 的命令，并编排 `service` 的执行
- 服务器框架目录设计中，`service` 目录下定义了部分相关内容，它们接收也会对来自 Boundary 的命令进行相应的编排

Entity 包含：
- 服务器框架目录设计中，`model` 目录下定义了所有服务器与 MySQL 相关的实体，承载系统数据
- 服务器在会话管理中，与 Redis 通讯的相关部分