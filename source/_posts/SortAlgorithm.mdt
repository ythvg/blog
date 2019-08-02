---
title: 排序算法
date: 2019-06-15 15:38:41
tags: data structure & algorithm
---
# 冒泡排序
[冒泡排序](https://zh.wikipedia.org/wiki/%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F)算法的运作如下：
1.比较相邻的元素。如果第一个比第二个大，就交换他们两个。
2.对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
3.针对所有的元素重复以上的步骤，除了最后一个。
4.持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。
```
function bubbleSort(arr) {
  for (let i = 0; i < arr.length - 1; i++) {
    for (let j = 0; j < arr.length - 1 - i; j++) {
        if (arr[j] > arr[j + 1]) swap(arr, j, j + 1)
    }
  }
};
```

# 选择排序
学则排序的思路就是找到数据结构中的最小值并将其放置到第一位，接着找到第二小的值并放到第二位，以此类推
选择排序同样是一个复杂度为O(n*2)的算法
```
function selectionSort(arr) {
  for (let i = 0; i < arr.length - 1; i++) {
    let indexMin = i
    for (let j = i + 1; j < arr.length - i) {
      if (arr[j] < arr[indexMin]) {
        indexMin = j
      }
    }
    if (i !== indexMin) {
      swap(arr, i, indexMin)
    }
  }
}
```