---
layout: post
title: Python搜索算法
date: 2016-05-06
categories: blog
tags: [Python]
description: “Python算法之搜索实现”
---

## 线性查找
线性查找有点简单粗暴，直接从第一个开始匹配，若符合则停止，并返回查找结果，若失败，可自定义返回结果。

```
def linear(list,b):
    for i in range(0,len(list)):
        if list[i]==b:
             return i
    return "do not exist"
a=[1,3,5,8,12,16,19,32,67]
print linear(a,67)
print linear(a,54)
```

可以看出，最多比较次数随着数列（列表）的大小增加而增加，呈线性关系。
## 二分查找

二分查找效率较高，但是它要求数组是有序序列。Python 内置函数sorted()可以直接将列表排序。二分查找的时间复杂度为`log n`

```
def binarysearch(list,b):
    low=0
    high=len(list)-1
    j="do not exsit"
    while low<high:
        c=(low+high)/2
        if b==list[c]:
            j=c
        if b<list[c]:
            high=c-1
        else:
            low=c+1
    return j
a=[1,3,5,8,12,15,32,45,67]
print binarysearch(a,12)
print binarysearch(a,13)
```
## 哈希搜索

书上并没有看到，上网搜索得出，通过哈希函数将输入值转换为小串数字或字母组合，缩小数据量。如一长串的数据可以通过哈希函数变为类似“a1b2”存储,将两者对应起来，搜索时找到a1b2就相当于找到对应的数据。不过可能存在冲突问题，即两个哈希值相同，对应的数据则有两个。具体实现方法暂时还没写，以后补吧。

## 合并两个数组（列表）

合并原理是两个列表逐个比较，将较小的元素添加进入新的列表，并在原列表删除元素。最后比较完成之后，不管哪个列表更长，都将剩余元素添加到新列表。
```
def MergeSort(l1, l2):
    tmp = []
    while len(l1) > 0 and len(l2) > 0:
        if l1[0] < l2[0]:
            tmp.append(l1[0])
            del l1[0]
        #elif l1[0]==l2[0]:
        #   tmp.append(l2[0])
        #   del l1[0]
        #  del l2[0]        #如果对应位置相同，则只添加一个
        else:
            tmp.append(l2[0])
            del l2[0]
    tmp.extend(l1)
    tmp.extend(l2)
    return tmp
L1=[1,3,6,8,12,34]
L2=[2,4,7,8,12,38,46]
print MergeSort(L1,L2)

```
结果是`[1, 2, 3, 4, 6, 7, 8, 8, 12, 12, 34, 38, 46]`重复元素没有检测，可以添加注释行，这样就正确了。也可以通过递归方式实现，但是递归处理有点麻烦。试了下斐波拉契函数，算到第四十个就CPU暴增，等待漫长才返回结果。貌似尾递归优化Python还不支持（用的2.7，最新未知）
