---
title: MongoDB数据库无法远程连接的解决方案
date: 2023/10/8 15:15:25
cover: ./images/bg.jpg
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
![mongodbconnection1.jpg](/screenshot/mongodbconnection1.jpg)
修改为
```
net:
  bindIp:0.0.0.0
```
![mongodbconnection2.jpg](/screenshot/mongodbconnection2.jpg)

**3. 重启mongoDB服务**
![mongodbconnection3.jpg](/screenshot/mongodbconnection3.jpg)