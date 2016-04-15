---
layout: post
title: 排序算法的几点记录
date: 2016-04-09
categories: blog
tags: [算法]
description: Python笔记
---

## 冒泡排序
1. 比较相邻的元素。如果第一个比第二个大，就交换他们两个。
2. 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
3. 针对所有的元素重复以上的步骤，除了最后一个。
4. 持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

用Python实现方法是:

```
 def BubbleSort(alist):
      for i in range(len(alist)-1,0,-1):
          for j in range(0,i)：
              if alist[j]>alist[j+1]:
                  alist[j],alist[j+1]=alist[j+1],alist[j]
      return alist
```

## 插入排序
插入排序算是最简单的排序，具体算法描述如下：

1.从第一个元素开始，该元素可以认为已经被排序

2.取出下一个元素，在已经排序的元素序列中从后向前扫描

3.如果该元素（已排序）大于新元素，将该元素移到下一位置

4.重复步骤3，直到找到已排序的元素小于或者等于新元素的位置

5.将新元素插入到该位置后

6.重复步骤2~5

Python实现算法
按照定义应该是这样：

```
def InsertSort(a):
    for j in range(1,len(a)):
        for i in range(j-1,0,-1):
            if a[j]<a[i]:
                a[j],a[i]=a[i],a[j]
    return a
a=[4,6,3,5,9,12,67,32]
print InsertSort(a)

```

看到有些资料上插入排序的算法是这样：


```
def InsertSort(alist):
    for i in range(0,len(alist)):
        for j in range(i+1,len(alist)):
            if alist[i]>alist[j]:
                alist[i],alist[j]=alist[j],alist[i]
    return alist
```

这不是类似于冒泡排序吗？

## 选择排序
原理是首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置，然后，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。以此类推，直到所有元素均排序完毕


## 区别
以序列`a=[1,6,3,5,9,12,67,32]`为例，第一轮排序的结果分别为：
- 冒泡排序
- 选择排序
- 插入排序 1,6,3,5,9,12,67,32

## 未完待续

存在一些错误，之后再补
