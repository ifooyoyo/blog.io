---
layout: post
title: 我常用的一些Linux命令
date: 2016-04-02
categories: blog
tags: [学习]
description: “都是自己常用的一些命令”
---
## 目录文件操作

首先确定当前所在目录`pwd`;目录就相当于Windows下的文件夹
再次切换路径，比如当前路径为`home/yoyo`(yoyo为我的用户名)，希望切换到home/test/test1/目录下，有两种方法：

1. cd ../test/test1
2. cd /home/test/test1

cd是change directory的缩写，切换路径的意思。第一种方法是使用相对路径，`.`指的是当前目录，`..`指的是上级目录，这里指的就是就是home目录；第二种用的是绝对路径。

如果没有home/test/test1目录怎么办？没关系，这里要用到mkdir命令新建目录。
`mkdir home/test/test1`

`ls` ls命令用于查看指定路径下的文件情况，如ls / 查看根目录下的文件夹 参数-a、-l用于查看文件属性和隐藏文件。

**新建文件**用`touch filename`就行，比如`touch test.txt`。用`vim test.txt`也可以创建并写入。

**移动文件**：mv home/test/test1 home/yoyo   mv命令还可以重命名文件，如`mv home/yoyo /home test`

想查看当前目录下文件，用`ls`命令就好，`ls [-a] yoyo/www/`查看的就是`www`目录下的文件。如果加上`-a`，隐藏文件也可以查看

**复制目录（文件）**：`cp directory(file) newpath`

**查找文件**：某个文件创建了不记得放哪了，自己的后缀或者文件名咋办？这时候就需要find命令了，find命令形式为：`find pathname -option [-print -exec -ok]，命令选项有`-name`、`-mtime -n/+n`等，例如
```find . -name *.txt//找出当前目录下所有txt文件：
find /home/yoyo -mtime -1   //根据文件更改时间（这里是一天内更改）查找文件

### 磁盘

'sudo fdisk -l' 查看当前磁盘分区情况

`df` 查看已挂载磁盘的总容量、使用容量、剩余容量等，一般加参数h方便查看

`du`

`mount`用于挂载磁盘，比如挂载sd2于mnt/2

## 任务管理

ps aux 命令可以查看当前运行的程序（进程），就像Windows下同时按`Enter Shift Esc`的任务管理器一样。
通过该命令可以查看当前运行程序的PID，类似于进程编号。接下来，可以使用kill 命令来杀死进程。

top 也是一个很不错的命令，作用于ps aux类似，侧重于查看进程占用资源情况。

top -u yoyo  查看yoyo用户的进程

## 网络操作
最常用的就是ping了，例如ping google.com（什么？ping不通，平常心），检查本机和目标主机的连通性。
还有一个就是ifconfig，查看ip地址
深入一点有mtr、tracepath等

## 其他
关机：`shutdown -h(-r) now` `-r`是重启

切换用户：`su username`

**很多命令刚开始可能很难记得那么多，多用就熟了，熟能生巧，真的。**

偷懒命令：alias，可以为命令起别称，例如alias l=“ls-al"，之后输入命令l就相当于输入ls -al了。

## 管道

相当于把前一个命令得输出作为后一个命令的输入，比如：
cat text.txt | grep ^u    //输出text.txt中以u开头的行

注:grep命令是一种强大的文本搜索工具，它使用正则表达式搜索文本

## 一些软件和书籍

vim ——编辑器之神

mocp ———终端音乐播放器

书籍：鸟哥的Linux私房菜。

其他命令和软件暂时没想到，以后再补。
