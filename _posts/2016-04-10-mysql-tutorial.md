---
layout: post
title: Mysql简明语法
date: 2016-04-10
categories: blog
tags: [语法,入门]
description: "mysql是最流行的数据库之一"
---
# 简明MySQL笔记

## 1 概念

- 数据库: 数据库是一些关联表的集合。
- 数据表: 表是数据的矩阵。在一个数据库中的表看起来像一个简单的电子表格。
- 列: 一列(数据元素) 包含了相同的数据, 例如邮政编码的数据。
- 行：一行（=元组，或记录）是一组相关的数据，例如一条用户订阅的数据。
- 约束：用于约束表中的数据规则，如果违反，则行为被终止。创建表或者创建表之后都可以规定。有NOT NULL（非空）、UNIQUE（唯一）、PRIMARY KEY、FOREIGN KEY等。
- 冗余：存储两倍数据，冗余可以使系统速度更快。
- 主键：主键是唯一的，一个数据表中只能包含一个主键，你可以使用主键来查询数据。
- 外键：外键用于关联两个表。
- 复合键：复合键（组合键）将多个列作为一个索引键，一般用于复合索引。
- 索引：使用索引可快速访问数据库表中的特定信息。索引是对数据库表中一列或多列的值进行排序的一种结构。类似于书籍的目录。
- 参照完整性: 参照的完整性要求关系中不允许引用不存在的实体。与实体完整性是关系模型必须满足的完整性约束条件，目的是保证数据的一致性。
- ACID：DBMS为了保证正确可靠必须具备的四个特性：原子性，一致性，隔离性，持久性

## 2 使用
环境 Cent os 6.5，安装mysql。

### 查看版本
mysqladmin –version

比如我的结果为mysqladmin  Ver 8.42 Distrib 5.1.73, for redhat-linux-gnu on i386

### 设置开机自启动
chkconfig mysqld on

MySQL安装成功后，默认的root用户密码为空，你可以使用以下命令来创建root用户的密码:

`mysqladmin -u root password "new_password"`

比如我的就是` mysqladmin -u root password "root"`

现在可以连接登录了：

mysql -u root -p    //输入密码

### 创建数据库

CREATE DATABASE yoyo；       //关键字大小写不敏感

删除用DROP DATABASE yoyo;

###  选择数据库

USE DATABASE;    //只有选择了数据库才能进行操作

### 创建表

CREATE TABLE mytable (name VARCHAR(20),age int,birth DATE);查看

 ![mytable](http://7xsx6z.com2.z0.glb.clouddn.com/show-tables.png)
###  显示表的结构

DESCRIBE mytable;   //语法为DESCRIBE TABLE_NAME

 ![mytable](http://7xsx6z.com2.z0.glb.clouddn.com/show-tables.png)

### 插入数据

插入数据用insert，
insert into mytable values("yoyo",22,'1993-07-11'); //你看，大小写确实不敏感

### 查看数据
select * from mytable

### 导入数据

导入：load data local infile 'dump.txt' into table mytable;
  ![mytable](http://7xsx6z.com2.z0.glb.clouddn.com/reselect-mytable.png)

警告的原因是txt文件中有两行是空的。删除数据：把两行空行删除。

delete from mytable where age=0；

记住 where语句用处大。
导出数据语法是 dump data

### 添加列
alter table mytable add birth_addr varchar(20);  //格式为 ALTER TABLE TABLE_NAME ADD COLUMN_NAME DATATYPE

### 添加约束
分为主键约束，值约束。这里添加主键约束。

alter table mytable add primary key (id);

### 更新数据

update命令主要是修改或者更新表数据，例如将yoyo的birth_addr修改，update……set where……

`update mytable set birth_addr="jishui" where name='yoyo'`

然后分别添加数据，最终结果：

 ![mytable](http://7xsx6z.com2.z0.glb.clouddn.com/final-select.png)

### 图形化交界面操作
navicat for mysql

![mytable](http://7xsx6z.com2.z0.glb.clouddn.com/navicat.png)

### 总结
- create：创建数据库、数据表，索引
- select：查看数据表
- update：更新数据库表中数据（表中数据的修改）
- delete：删除数据表中的数据
- insert into：增加（插入）新数据
- alter ：已有的表中添加、删除、修改列(主要是整个表的操作)
- drop ： 删除数据库、表、索引
- 增删查改常常结合 where语句使用

### 注意
语句以`；`结尾，关键字大小写不敏感。数据库表的操作主要包含增删查改。

这里只是简单入门以及使用，包括通配符，视图，数据类型，函数等知识还未开始介绍，以后再补。

