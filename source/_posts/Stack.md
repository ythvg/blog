---
title: 栈
date: 2019-06-15 15:37:12
tags:
---
- [栈](https://zh.wikipedia.org/wiki/%E5%A0%86%E6%A0%88)是一种后入先出（LIFO，last-in-ﬁrst-out）的数据结构
- 栈使用两种基本操作：推入（压栈，push）和弹出（弹栈，pop）
- 在javascript中，栈可以看成是数组的子集

![](https://upload-images.jianshu.io/upload_images/3373227-36db9c83b8fcb1a0.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 1、实现
```
class Stack{
    constructor() {
        this.stack= [];
    }
    push(item) {
        this.stack.push(item);
    }
    pop() {
        this.stack.pop();
    }
}
```

# 2、应用

### 数制间的相互转换
可以利用栈将一个数字从一种数制转换成另一种数制。假设想将数字 n 转换为以 b 为基数 的数字，实现转换的算法如下:
1. 最高位为 n % b，将此位压入栈
2. 使用 n/b 代替 n
3. 重复步骤 1 和 2，直到 n 等于 0，且没有余数
4. 持续将栈内元素弹出，直到栈为空，依次将这些元素排列，就得到转换后数字的字符 串形式
```
function mulBase(num, base) {    
    const s = new Stack();
    do {
        s.push(num % base);    
        num = Math.floor(num /= base);
    } while (num > 0);
    let converted = "";
    while (s.length() > 0) {
        converted += s.pop();
    }    
    return converted;
}

```

###  [括号匹配](https://leetcode.com/problems/valid-parentheses/)
```
/**
 * @param {string} s
 * @return {boolean}
 */
function isValid(s) {
    const stack = [];
    const mapping = {
        ')': '(',
        '}': '{',
        ']': '['
    };
    for (v of s) {
        if (v in mapping) {
            let top_el = stack.pop();
            if (top_el !== mapping[v]) {
                return false;
            }
        } else {
            stack.push(v)
        }
    }
    return stack.length === 0;
};
```