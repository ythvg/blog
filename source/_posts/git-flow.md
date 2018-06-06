---
title: 团队协作流程
date: 2018-06-06 10:30:16
tags:
---

在团队开发中，如果没有一个有效的工作流程和代码规范，那么在进行团队协作的时候就不可避免的导致各种混乱，从而导致维护成本和迭代成本的大幅度增加。

## 项目命名

对于前后端分离项目，在项目命名上建议遵循

> 前端： xxx_frontend， 后端：xxx_backend

的命名方式，且所有项目和分支的命名应采用 **小写字母** 加 **_** 的方式


## git 流程

* 使用git flow流程进行开发

    * 什么是 [git flow](https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/git-flow) ? 

    * git flow [备忘清单 ](https://danielkummer.github.io/git-flow-cheatsheet/index.html)

* git flow 重点

    * master 不能直接工作在这个 master 分支上，而是在其他指定的，独立的特性分支中，不直接提交改动到 master 分支上也是很多工作流程的一个共同的规则

    * develop 是进行任何新的开发的基础分支。当开始一个新的功能分支时，它将是开发的基础。另外，该分支也汇集所有已经完成的功能，并等待被整合到 master 分支中

    * feature 开发新功能应该新建一个独立的feature分支，如 feature/xxx


## 软件架构


* 软件在架构设计时建议采用自顶向下的设计思想，尽量的做到模块化和抽象化

    * 自顶向下设计， 就是设计时首先要对项目有一个全面的了解， 然后从顶层开始，一步一步的细分实现，设计思想有点类似于 java 和 typescript 中 接口的实现

    * 模块化开发应当尽量降低代码的耦合度，从而让团队开发更加高效

    * 在自定义函数方面建议遵循 do_something 的开发哲学，就是一个函数就是完成一个功能


* 代码风格和代码检查

    * 推荐使用 [EditorConfig](https://editorconfig.org/) 进行代码风格约束

    * 关于各类代码检查工具 xxlint 小型项目不推荐使用

* 代码质量尽量做到可阅读性和简单性

    * 单个文件尽量不要超过300行

    * 不要引入过多无用的第三方类库从而导致代码臃肿
