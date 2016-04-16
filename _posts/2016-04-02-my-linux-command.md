---
layout: post
title: 我常用的一些Linux命令
date: 2016-04-02
categories: blog
tags: [学习]
description: 都是自己常用的一些命令
---
## 目录操作

首先确定当前所在目录`pwd`;目录就相当于Windows下的文件夹
再次切换路径，比如当前路径为`home/yoyo`(yoyo为我的用户名)，希望切换到home/test/test1/目录下，有两种方法：

1. cd ../test/test1
2. cd /home/test/test1

cd是change directory的缩写，切换路径的意思。第一种方法是使用相对路径，`.`指的是当前目录，`..`指的是上级目录，这里指的就是就是home目录；第二种用的是绝对路径。

如果没有home/test/test1目录怎么办？没关系，这里要用到mkdir命令新建目录。
`make home/test/test1`
新建文件用`touch filename`就行，比如`touch test.txt`。用`vim test.txt`也可以创建。

想查看当前目录下文件，用`ls`命令就好，`ls [-a] yoyo/www/`查看的就是`www`目录下的文件。如果加上`-a`，隐藏文件也可以查看




## 任务管理
ps aux 命令可以查看当前运行的程序（进程），就像Windows下同时按`Enter Shift Esc`的任务管理器一样。
通过该命令可以查看当前运行程序的PID，类似于进程编号。接下来，可以使用kill 命令来杀死进程。

top 也是一个很不错的命令，作用于ps aux类似，侧重于查看进程占用资源情况。



## 网络操作
最常用的就是ping了，例如ping google.com（什么？ping不通，平常心），检查本机和目标主机的连通性。
还有一个就是ifconfig，查看ip地址

## 其他
关机：`shutdown -h(-r) now` `-r`是重启
whoios

## 一些软件

vim ——编辑器之神

mocp    ———终端音乐播放器

其他命令和软件暂时没想到，以后再补。
