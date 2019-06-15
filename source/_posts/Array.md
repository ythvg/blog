---
title: 数组
date: 2019-06-15 15:30:30
tags: data structure & algorithm
---

# 1、数组的定义

- 一个存储元素的线性集合（collection），元素可以通过索引来任意存取，索引通常是数字，用来计算元素之间存储位置的偏移量。

JavaScript 中的数组是一种特殊的对象，用来表示偏移量的索引是该对象的属性，索引可 能是整数。然而，这些数字索引在内部被转换为字符串类型，这是因为 JavaScript 对象中的属性名必须是字符串。数组在 JavaScript 中只是一种特殊的对象，所以效率上不如其他 语言中的数组高。

# 2、使用数组

### 创建数组
```
// 通过 [] 操作符声明一个数组变量
var numbers = [];
var numbers = [1,2,3,4,5];
```
```
// 调用 Array 的构造函数创建数组
var numbers = new Array(); 
var numbers = new Array(1,2,3,4,5);  //可以为构造函数传入一组元素作为数组的初始值
var numbers = new Array(10);  //可以只传入一个参数，用来指定数组的长度
```

### 由字符串生成数组
调用字符串对象的 split() 方法也可以生成数组。该方法通过一些常见的分隔符，比如分 隔单词的空格，将一个字符串分成几部分，并将每部分作为一个元素保存于一个新建的数 组中
```
var sentence = "the quick brown fox jumped over the lazy dog"; 
var words = sentence.split(" "); 
```

### Array.from()
从类数组对象或者可迭代对象中创建一个新的数组实例
```
Array.from('foo');  // Array ["f", "o", "o"]
```

### 判断是否数组类型
可以调用 Array.isArray() 来判断一个对象是否是数组

# 3、数组访问函数
JavaScript 提供了一组用来访问数组元素的函数，这些函数返回目标数组的某种表现

### 查找元素
indexOf() 和 lastIndexOf()函数是最常用的存取函数之一，用来查找传进来的参数在目标数组中是否存在。 如果目标数组包含该参数，就返回该元素在数组中的索引；如果不包含，就返回 -1。如果数组中包含多个相同的元素，indexOf() 函数总是返回第一个与参数相同的元素的索 引
```
var names = ["David", "Cynthia", "Raymond", "Clayton", "Jennifer"]; 
names.indexOf("Cynthia")  // 1
```
find() 方法返回数组中满足提供的测试函数的第一个元素的值。否则返回undefined
```
arr.find(callback[, thisArg])
```

### 数组的字符串表示
有两个方法可以将数组转化为字符串：join() 和 toString()
```
arr.join([separator])
```

### 由已有数组创建新数组
concat 方法可以合并多个数组创建一个新数组，slice() 方法截取一个数组的子集创建一个新数组
```
array.concat(value1[, value2[, ...[, valueN]]])
array.slice(begin, end);
```

# 4、可变函数
JavaScript 拥有一组可变函数，使用它们，可以不必引用数组中的某个元素，就能改变数组内容

### 为数组添加元素
有两个方法可以为数组添加元素：push() 和 unshift()。

### 从数组中删除元素
使用 pop() 方法可以删除数组末尾的元素，shift() 方法可以删除数组的第一个元素

### 从数组中间位置添加和删除元素
使用 splice() 方法
```
array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
```

### 为数组排序
reverse() 方法将数组中元素的位置颠倒,并返回该数组。该方法会改变原数组
sort()方法用原地算法对数组的元素进行排序，并返回数组
```
arr.sort([compareFunction])
```

# 5、迭代器方法
迭代器方法方法对数组中的每个元素应用一个函数，可以返回一个 值、一组值或者一个新数组

###  不生成新数组的迭代器方法
forEach()方法接受一个函数作为参数，对数组中的每个元素使用该函数
```
arr.forEach(callback[, thisArg]);
```
every() 方法测试数组的所有元素是否都通过了指定函数的测试
```
arr.every(callback[, thisArg])
```
some() 方法测试是否至少有一个元素通过由提供的函数实现的测试
```
arr.some(callback(element[, index[, array]])[, thisArg])
```

reduce() 方法对数组中的每个元素执行一个由您提供的reducer函数(升序执行)，将其结果汇总为单个返回值。reduceRight则反方向执行
```
arr.reduce(callback[, initialValue])
```

###  生成新数组的迭代器方法 
map() 方法创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果
```
var new_array = arr.map(function callback(currentValue[, index[, array]]) {
 // Return element for new_array }[, 
thisArg])
```
filter() 方法创建一个新数组, 其包含通过所提供函数实现的测试的所有元素
```
var newArray = arr.filter(callback(element[, index[, array]])[, thisArg])
```

