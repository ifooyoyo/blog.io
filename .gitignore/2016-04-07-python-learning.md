---
layout: post
title: Python笔记之装饰器
date: 2016-04-08
categories: blog
tags: [笔记]
description: 思考
---
## 什么是装饰器

python中万物皆对象，number,string,tuple,list,dict;function,class,module……都属于对象。举例来说，将函数对象赋值给变量，并且调用：

def helloworld():
    print "hello world"
f=helloworld
print f()

装饰器作用是动态增加函数的功能，在不改变原函数的基础上
