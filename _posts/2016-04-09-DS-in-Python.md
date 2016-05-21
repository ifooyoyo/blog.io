---
layout: post
title: 排序算法的几点记录
date: 2016-04-09
categories: blog
tags: [读书]
description: "Python笔记"
---

## 冒泡排序
1. 比较相邻的元素。如果第一个比第二个大，就交换它们两个。
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

Python实现算法，按照定义应该是这样：

```
def InsertSort(alist):
    for i in range(0,len(alist)):
        for j in range(i+1,len(alist)):
            if alist[i]>alist[j]:
                alist[i],alist[j]=alist[j],alist[i]
    return alist
```



## 选择排序

原理是首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置，然后，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。以此类推，直到所有元素均排序完毕

```
def selectionSort(alist):
    for i in range(len(alist)-1,0,-1):
        maxone = 0
        for j in range(1,i+1):
            if alist[j]>alist[maxone]:
                maxone = j      //找出最大元素的标的
        temp = alist[i]
        alist[i] = alist[maxone]
        alist[maxone] = temp   //将最大元素赋值给最后一位元素
    return alist
if __name__ == '__main__':
    alist = [54,26,93,17,77,31,44,55,20]
    selectionSort(alist)
    print alist
```

## 区别

以序列`a=[1,6,3,15,9,8,67,32]`为例，第一轮排序的结果分别为：

- 冒泡排序 1,3,6,9,8,15,32,67

- 插入排序 1,6,3,15,9,8,67,32

- 选择排序 1,6,3,15,9,8,32,67

排序方法 | 时间复杂度 | 空间复杂度
----     |------      |----
冒泡     |  O(n2)     | O(1)
插入     |  O(n2)     | O(1)
选择     |  O(n2)     | O(1)

## 未完待续

部分参考自维基百科。

推荐:[可视化数据结构](http://zh.visualgo.net/)
