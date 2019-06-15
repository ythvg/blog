---
title: 散列表
date: 2019-06-15 15:38:08
tags: data structure & algorithm
---
散列算法的作用是尽可能快地在数据结构中找到一个值。散列函数的作用是给定一个键值，然后返回值在表中的地址

# 基本实现
```
class HashTable {
    constructor() {
        this.table = [];
    }
    put(key, value) {
        const position = this.loseloseHashCode(key);
        this.table[position] = value;
    }
    get(key) {
        return this.table[loseloseHashCode(key)];
    }
    remove(key) {
        this.table[loseloseHashCode(key)] = undefined;
    }
    loseloseHashCode(key) {
        let hash = 0;
        for (let i = 0; i < key.length; i++) {
            hash += key.charCodeAt(i);
        }
        // 为了得到比较小的数值，我们会使用hash值和一个任意数做除法的余数
        return hash % 37;
    }
}
```

# 碰撞处理
### 分离链接法
分离链接法包括为散列表的每一个位置创建一个链表并将元素存储在里面。它是解决冲突的最简单的方法，但是它在HashTable实例之外还需要额外的存储空间
```
class HashTable {
    constructor() {
        this.table = [];
    }
    put(key, value) {
        const LList = this.table[this.loseloseHashCode(key)];
        const valuePair = { key, value };
        if (LList === undefined) {
            LList = new LinkedList();
        }
        table[position].append(valuePair);
    }
    get(key) {
        const LList = this.table[this.loseloseHashCode(key)];
        if (LList !== undefined) {
            let curNode = LList.head;
            while(curNode.next) {
                if (curNode.next.key === key) {
                    return curNode.next.item.value;
                }
                curNode = curNode.next;
            }
        }
        return undefined;
    }
    remove(key) {
        const LList = this.table[this.loseloseHashCode(key)];
        if (LList !== undefined) {
            let curNode = LList.head;
            while(curNode.next) {
                if (curNode.next.key === key) {
                    LList.remove(key);
                    return true;
                }
            }
        }
        return false;
    }
    loseloseHashCode(key) {
        let hash = 0;
        for (let i = 0; i < key.length; i++) {
            hash += key.charCodeAt(i);
        }
        // 为了得到比较小的数值，我们会使用hash值和一个任意数做除法的余数
        return hash % 37;
    }
}
```
### 线性探测法
另一种解决冲突的方法是线性探查。当想向表中某个位置加入一个新元素的时候，如果索引为index的位置已经被占据了，就尝试index+1的位置。如果index+1的位置也被占据了，就尝试index+2的位置，以此类推

# 创建更好的散列函数
```
function djb2HashCode (key) {
    var hash = 5381; // 初始化一个hash变量并赋值为一个质数（大多数实现都使用5381）
    for (var i = 0; i < key.length; i++) { 
    // 将hash与33相乘（用来当作一个魔力数），并和当前迭代到的字符的ASCII码值相加
        hash = hash * 33 + key.charCodeAt(i); //{3}
    }
   // 最后将使用相加的和与另一个随机质数（比我们认为的散列表的大小要大， 比如1000）相除的余数
    return hash % 1013; 
}; 
```