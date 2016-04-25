---
layout: post
title: 我的Vim配置学习之路
date: 2016-04-14
categories: blog
tags: [配置]
description: vim配置
---
## 为何用vim

毫无疑问，高度自由、高效。当然，一切都是你掌握之后。如果用习惯了IDE，其实也差不多。因为VIM开发其实你还是把它配置为一个IDE——但这就是高度自由的来源：几乎随意设置的快捷键。至于高效，主要是插件的原因了，Vim有大量的优秀开发插件，满足你的各种需求。毕竟，作为最受欢迎的编辑器，Vim被称为编辑器之神不是吹牛的。

## 简介
第一次安装Vim后打开，你肯定忍不住吐槽，还不如windows的notepad呢。别急，慢慢来——vim可以让你想怎么配怎么配。

配置vim需要修改vim的配置文件`vimrc`，如果没有，则新建一个。`mkdir .vimrc`,注意是在目录`~`下创建。

## 配置

简单配置
```
"syntax
syntax enable
"语法高亮
syntax on
"开启文件类型检测
filetype on
"开启实时搜索
set incsearch
set hesearch
"高亮当前行和列
set cursorline
set cursorcolumn
"忽略大小写
set ignorecase
"显示行号
set number
set wildmenu
set ruler
set nocompatible
"配色方案
set background
colorscheme molokai
```
## 插件

插件才是重点，一些常用插件有Vundle（插件管理器），YouCompleteMe（代码补全,名字取得多浪漫），主题等，其他插件根据开发而定。

## 搬运工

[Vim配置、插件和使用技巧](http://www.jianshu.com/p/a0b452f8f720)
[vim配置详解](http://www.cnblogs.com/ma6174/archive/2011/12/10/2283393.html)
[简明 Vim 练级攻略](http://coolshell.cn/articles/5426.html)

## 后话

炫技不是学习Vim的目的，也许你最终还是用IDE开发，但是，通过配置VIM，你可以学到很多东西，比如DIY，比如插件安装——最重要的是动手做一件东西。

推荐一个傻瓜式的配置方案，读一读文档了解快捷键就可以了。spf13
