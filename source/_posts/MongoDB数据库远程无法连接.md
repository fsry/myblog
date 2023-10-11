---
title: MongoDB数据库无法远程连接的解决方案
date: 2023/10/8 15:15:25
cover: https://cdn.jsdelivr.net/gh/fsry/myblog/source/images/bg.jpg
coverWidth: 3840
coverHeight: 2244
categories: 工作中の奇怪问题
tags: MongoDB
---
# 修复了MongoDB数据库无法远程连接的问题
## 排查方向：
**1. 确认防火墙是否关闭或防火墙规则是否正确**

**2. 修改/MongoDB/Server/版本号/bin/mongod.cfg文件**
从
 ```
net:
  bindIp:127.0.0.1
```
![](./MongoDB数据库远程无法连接/MongoDBConnection1.JPG)
修改为
```
net:
  bindIp:0.0.0.0
```
![](./MongoDB数据库远程无法连接/MongoDBConnection2.JPG)

**3. 重启mongoDB服务**
![](./MongoDB数据库远程无法连接/MongoDBConnection3.JPG)