---
title: nosql-manager-for-mongoDB数据查询用法
date: 2024/07/25 08:25:55
cover: /2024/07/25/query.png
coverWidth: 1920
coverHeight: 1080
categories: 工作中の奇怪问题
tags: MongoDB
---
最近因为一些原因，不得不直接进数据库改数据，数据量又不大，比起搓一个脚本不如自己手动查找修改，于是有了这篇博客
在MongoDB中，Query、Projection和Order是常用的查询操作，分别用于筛选数据、指定返回字段和排序结果。以下是详细的介绍和用法：
假设存在以下结构结构
```
{
  "_id": 1,
  "name": "David",
  "age": 16,
  "friend":[{
    "id":2
    "name":"Lucy",
    "othermessage":{
        "hobby":"travel",
        "height":"165",
        "weight":"60kg"
    }
  },
    { "id":3
    "name":"rebecca",
    "othermessage":{
        "hobby":"shot",
        "height":"155",
        "weight":"45kg"
    }}]
}
```
1. Query（查询）
Query用于指定查询条件，以筛选集合中的文档。可以使用各种条件运算符来构建查询。
-  基本查询示例
查询特定字段的文档：
```{"name":"David"}```
返回name为David的
