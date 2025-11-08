# Git学习笔记

> -师梓怡

## 一、核心概念

Git 是一款 分布式版本控制系统，可追踪文件修改历史、管理不同版本，并支持多人协作开发。

## 二、必备基础操作

### 初始化与配置

- 新建仓库：在项目文件夹中执行  git init ，生成隐藏的  .git  目录（仓库核心文件）。
- 配置用户信息（首次使用）：

git config --global user.name "你的名字"  
git config --global user.email "你的邮箱"  

## 三、3个核心命令

1.git add . ：把所有修改的文件“暂存”起来

2.git commit -m "备注" ：把暂存的文件“提交”到本地仓库

> m后面要保留空格

3.git status ：随时查看文件状态

## 四.分支管理

1.创建分支： git branch 分支名 

>git branch dev  创建开发分支

2.切换分支： git switch 分支名

>  git switch dev  切换到开发分支

3.合并分支：完成开发后，切回**主分支**，执行  git merge 分支名  合并代码

参考链接：[笔记]([远程仓库 - Git教程 - 廖雪峰的官方网站](https://liaoxuefeng.com/books/git/remote/index.html))

## 五.常见指令

### 1.基础配置（首次使用必做）

- 配置用户名： git config --global user.name "你的用户名" 
- 配置邮箱： git config --global user.email "你的邮箱" 
- 查看配置： git config --list 

### 2.仓库操作

- 初始化本地仓库： git init 

- 克隆远程仓库： git clone 仓库地址 

  > （HTTPS/SSH 均可）

- 关联远程仓库： git remote add origin 仓库地址 

- 查看远程仓库： git remote -v 

### 3.代码暂存与提交

- 查看文件状态： git status 

  > 简化输出： git status -s 

- 添加文件到暂存区： git add 文件名 

  > 全部添加： git add . 

- 撤销暂存区文件： git reset HEAD 文件名 

- 提交暂存区代码： git commit -m "提交说明" 

- 撤销本地未提交修改： git checkout -- 文件名 

### 4.分支管理

- 查看所有分支： git branch 

  > 远程分支： git branch -r 

- 创建分支： git branch 分支名 

  > 创建并切换： git checkout -b 分支名 

- 切换分支： git checkout 分支名 

  > 新版 Git 可用： git switch 分支名 

- 合并分支： git merge 待合并分支名 

  > 需先切换到目标分支

- 删除分支： git branch -d 分支名 

  > 强制删除未合并分支： git branch -D 分支名 

### 5.远程同步

- 拉取远程代码： git pull 

  > =  git fetch + git merge 

- 推送本地代码： git push origin 分支名

  > 首次推送： git push -u origin 分支名 

- 拉取远程分支到本地： git fetch origin 远程分支名:本地分支名 

### 6.版本查看与回溯

- 查看提交记录： git log 

  > 简化： git log --oneline 

- 查看操作日志

  > 可恢复删除内容： git reflog 

- 回退到指定版本： git reset --hard 提交ID 

  > 提交ID通过  git log  获取

### 7.其他常用

- 忽略文件配置：在仓库根目录创建  .gitignore  文件，写入需忽略的文件名/目录

- 查看分支差异： git diff 分支1 分支2 

- 暂存当前修改（切换分支用）： git stash 

  > 恢复： git stash pop 







