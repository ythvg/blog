---
title: 队列
date: 2019-06-15 15:37:19
tags: data structure & algorithm
---
队列是遵循FIFO（First In First Out，先进先出）原则的一组有序的线性结构

![](https://upload-images.jianshu.io/upload_images/3373227-08871fd518416e80.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 实现
```
class Queue {
    constructor() {
        this.queue = [];
    }
    enQueue(item) {
        this.queue.push(item);
    }
    deQueue() {
        this.queue.shift();
    }
}
```

# 优先队列
优先队列中元素的添加和移除是基于优先级的。一个现实的例子就是机场登机的顺序。头等舱和商务舱乘客的优先级要高于经济舱乘客
```
class PriorityQueue {
    constructor() {
        this.queue = [];
    }
    enQueue(item, priority) {
        let queueItem = { item, priority };
        let added = false;
        for (let i = 0; i < this.queue.length; i++) {
            if (priority < this.queue[i].priority) {
                this.queue.splice(i, 0, queueItem);
                added = true;
                break;
            }
        }
        if (!added) {
            this.queue.push(queueItem);
        }
    }
    deQueue() {
        this.queue.shift();
    }
}
```

# 循环队列
循环队列的一个例子就是击鼓传花游戏（HotPotato）。在这个游戏中，孩子们围成一个圆圈，把花尽快地传递给旁边的人。某一时刻传花停止，这个时候花在谁手里，谁就退出圆圈结束游戏。重复这个过程，直到只剩一个孩子（胜者）
```
function hotPotato(nameList, num) {
    let queue = new queue();
    for (let i = 0; i < nameList.length; i++) {
        queue.enQueue(nameList[i]);
    }
    while(queue.size() > 1) {
        for (let i = 0; i < num; i++) {
            queue.enQueue(queue.deQueue());
        }
        queue.deQueue(); // 被淘汰
    }
    return queue.deQueue();
}
```

# javascript任务队列
当我们在浏览器中打开新标签时，就会创建一个任务队列。这是因为每个标签都是单线程处 理所有的任务，它被称为事件循环。浏览器要负责多个任务，如渲染HTML，执行JavaScript代码， 处理用户交互（用户输入、鼠标点击等），执行和处理异步请求。