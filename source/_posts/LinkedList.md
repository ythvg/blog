---
title: 链表
date: 2019-06-15 15:37:37
tags: data structure & algorithm
---
链表存储有序的元素集合，但不同于数组，链表中的元素在内存中并不是连续放置的。每个元素由一个存储元素本身的节点和一个指向下一个元素的引用（也称指针或链接）组成

![](https://upload-images.jianshu.io/upload_images/3373227-0e766273d5619430.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 为什么使用链表
数组的大小是固定的，从数组的起点或中间插入或移除项的成本很高，因为需要移动元素。链表的一个好处在于，添加或移除元素的时候不需要移动其他元素，因此插入一个元素的效率很高。
数组的另一个细节是可以直接访问任何位置的任何元素，而要想访问链表中间的一个元素，需要从起点（表头）开始迭代列表直到找到所需的元素。

# 实现
```
class Node {
    constructor(item) {
        this.item = item;
        this.next = null;
    }
 }
 
 class LinkedList {
     constructor() {
         this.head = new Node("head");
     }
     find(item) {
         let curNode = this.head;
         while(curNode.item !== item) {
             curNode = curNode.next;
         }
         return curNode
     }
     insert(newItem, item) {
         const newNode = new Node(newItem);
         const curNode  = this.find(item);
         newNode.next = curNode.next;
         curNode.next = newNode;
     }
     append(item) {
         const curNode = this.head;
         while(curNode.next) {
             curNode = curNode.next;
         }
         curNode.next = item;
     }
     findPrevious(item) {
         let prevNode = this.head;
         while(prevNode.next && prevNode.next.item !== item) {
             prevNode = prevNode.next;
         }
         return prevNode;
     }
     remove(item) {
         const prevNode = this.findPrevious(item);
         prevNode.next = prevNode.next.next;
     }
     display() {
         let curNode = this.head.next;
         while(curNode !== null) {
             console.log(curNode.item);
             curNode = curNode.next;
         }
     }
 }
 
```