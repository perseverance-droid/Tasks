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



