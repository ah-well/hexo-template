---
title: GitLearn
date: 2019-04-11 15:56:23
tags:
---

## 什么是Git
> linus用C语言写的分布式版本控制系统。前者有CVS、SVN这些集中式的版本控制系统，但速度慢，且需联网，另有一些系统比这两者好用，不过需要付费，与Linux的开源精神不符，如BitKeeper。也正是它的东家BitMover公司因为开发Samba的Andrew试图破解BitKeeper的协议（据说不止他一个），要收回Linux社区的免费使用权，才迫使Linus在两周之内自己动手用C写了一个分布式版本控制系统。并在一个月内转移Linux的源码由Git来管理了。
 ---
## 集中式vs分布式
-  集中式和分布式，一个版本对应多个版本
-  集中式必须联网才能工作，无网络状态下无法回退到之前的某个版本
-  Git速度快、灵活，任意两个开发者之间可以很容易的解决冲突。

  - Git代码保密性差，一旦开发者把整个库克隆下来就可以完全公开所有代码和版本信息。学习周期长
---
##  Git基本概念
- 工作区：就是你在电脑里能看到的目录。
- 暂存区：英文叫stage, 或index。一般存放在 ".git目录下" 下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
- 版本库：工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。

### Git工作流
- 克隆 Git 资源作为工作目录。
- 在克隆的资源上添加或修改文件。
- 如果其他人修改了，你可以更新资源。
- 在提交前查看修改。
- 提交修改。
- 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。
  
  ![工作流](https://7n.w3cschool.cn/attachments/day_160929/201609291518243574.png)


### git创建仓库
```
git init                    在当前目录下创建Git仓库
git init newrepo            使用指定目录作为Git仓库
git add                     命令可将该文件添加到缓存

git status                  命令用于查看项目的当前状态
git status -s               简短的结果输出。如果没加该参数会详细输出内容
git diff                    显示已写入缓存与已修改但尚未写入缓存的改动的区别
  git diff --cached         查看已缓存的改动
  git diff HEAD             查看已缓存的与未缓存的所有改动
  git diff --stat           显示摘要而非整个diff

git commit                  记录缓存区的快照
  git commit -m             记录缓存提供提交注释
  git commit -a             跳过git add 提交缓存的流程

git reset HEAD              取消缓存已缓存的内容
  git reset HEAD -- [文件名] 
git rm                      将文件从缓存区中移除，默认情况下，会将文件从缓存区和你的硬盘中（工作目录）删除      
  git rm --cached           在工作目录中留着该文件，仅删除缓存区的文件
  git mv                    相当于git rm --cached 有点多余

// 初始化后，在当前目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中。
// 如果当前目录下有几个文件想要纳入版本控制，需要先用 git add 命令告诉 Git 开始对这些文件进行跟踪，然后提交：
git add *.c         
git add README
git commit -m 'initial project version'

// 从现有仓库克隆，如果要自己定义要新建的项目目录名称，可以在上面的命令末尾指定新的名字：
git clone [url]       

```

### 分支管理
```
  git branch (branchname)           创建分支
  git checkout (branchname)         切换分支
  git merge                         合并分支

  git branch                        列出分支

```