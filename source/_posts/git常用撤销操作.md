---
title: git常用撤销操作
date: 2018-02-01 17:28:34
categories: "coding"
tags:
  - git
---

![git-lifecycle](git常用撤销操作/lifecycle.png)

### 基本状态标识

+ **A-** = `untracked` - 未跟踪
+ **A** = `tracked` - 已跟踪未修改
+ **A+** = `modified` - 已修改未暂存
+ **B** = `staged` - 已暂存未提交
+ **C** = `committed` - 已提交未PUSH

### 各状态之间的变化

+ **A-** -> **B**: `git add <FILE>`
+ **B** -> **A-**: `git rm --cached <FILE>`
+ **B** -> 删除不保留文件: `git rm -f <FILE>`
+ **A** -> **A-**: `git rm --cached <FILE>`
+ **A** -> **A+**: 修改文件
+ **A+** -> **A**: `git checkout -- <FILE>`
+ **A+** -> **B**: `git add <FILE>`
+ **B** -> **A+**: `git reset HEAD <FILE>`
+ **B** -> **C**: `git commit -m "message"`
+ **C** -> **B**: `git reset --soft HEAD^`
+ 修改最后一次提交: `git commit --amend`

非常实用。转载自[@Netpi](http://www.netpi.me/uncategorized/gitrevoke/)
