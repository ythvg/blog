---
title: 团队协作流程
date: 2018-06-06 10:30:16
tags:
---

在团队开发中，如果没有一个有效的工作流程和代码规范，那么在进行团队协作的时候就不可避免的导致各种混乱，从而导致维护成本和迭代成本的大幅度增加。

## 项目命名

对于前后端分离项目，在项目命名上建议遵循

> 前端： xxx-frontend， 后端：xxx-backend

的命名方式，且所有项目和分支的命名采用 **小写字母** 加 **-** 的方式


## 软件版本控制

* 推荐使用git flow流程进行开发

    * 什么是 [git flow](https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/git-flow) ? 

    * git flow [备忘清单 ](https://danielkummer.github.io/git-flow-cheatsheet/index.html)

* git flow 主要分支

    * master 不能直接工作在这个 master 分支上，而是在其他指定的，独立的特性分支中，不直接提交改动到 master 分支上也是很多工作流程的一个共同的规则

    * develop 是进行任何新的开发的基础分支。当开始一个新的功能分支时，它将是开发的基础。另外，该分支也汇集所有已经完成的功能，并等待被整合到 master 分支中

    * feature 开发新功能应该新建一个独立的feature分支，如 feature/xxx


## 软件架构

* 软件在架构设计时建议采用自顶向下的设计思想，尽量的做到模块化和抽象化

