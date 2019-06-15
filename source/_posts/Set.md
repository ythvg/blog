---
title: 集合
date: 2019-06-15 15:37:45
tags: data structure & algorithm
---
集合是由一组无序且不重复的元素组成的

# 语法
```
new Set([iterable]); // 如果传递一个[可迭代对象]，它的所有元素将不重复地被添加到新的 Set 中。
set.add(value)  // 添加值，返回 set 自身
set.delete(value)  // 删除值，如果该 value 在调用方法的时候存在则返回 true ，否则返回 false
set.has(value)  // 如果 set 中存在该值则返回 true ，否则返回 false
set.clear() // 清空 set
set.size  // 元素个数

set.keys()  // 返回 set 中值的迭代对象
set.values() // 和 set.keys 一样
set.entries() // 返回形如 [value, value] 的迭代对象，为了兼容 Map 而存在。
```
# Set迭代
可以使用 for..of 或者 forEach 来循环查看 set
```
for (let value of set) alert(value);

set.forEach((value, valueAgain, set) => {
  alert(value);
});
```

# 应用
### 数组去重
```
// Use to remove duplicate elements from the array 
const numbers = [2,3,4,4,2,3,3,4,4,5,5,6,6,7,5,32,3,4,5]
console.log([...new Set(numbers)]) 
// [2, 3, 4, 5, 6, 7, 32]
```