---
title: 字典
date: 2019-06-15 15:37:51
tags: data structure & algorithm
---
字典是一种以键 - 值对形式存储数据的数据结构

# 语法
```
new Map([iterable])
map.set(key, value) // 根据键（key）存储值（value），返回该Map对象
map.get(key) // 根据键返回值，如果 map 中该键不存在，返回 undefined
map.has(key) // 如果键存在，返回 true，否则返回 false
map.delete(key) // 移除该键的值
map.clear() // 清空 map
map.size // 返回当前元素个数

// 迭代 Map
map.keys() – 返回键的迭代器，
map.values() – 返回值的迭代器，
map.entries() – 返回 [key, value] 迭代器入口，for..of 循环会默认使用它
```

# Object 和 Map 对比
- 一个Object的键只能是字符串或者Symbols，但一个 Map 的键可以是任意值，包括函数、对象、基本类型
- Map 中的键值是有序的，而添加到对象中的键则不是。因此，当对它进行遍历时，Map 对象是按插入的顺序返回键值
 - 可以通过 size 属性直接获取一个 Map 的键值对个数，而 Object 的键值对个数只能手动计算
- Map 可直接进行迭代，而 Object 的迭代需要先获取它的键数组，然后再进行迭代
- Map 在涉及频繁增删键值对的场景下会有些性能优势
