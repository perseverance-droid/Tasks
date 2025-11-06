# GitHub 学习笔记

## 一、核心概念速记

- 仓库（Repository）：存储项目代码、文档的“文件夹”，分公开（Public）和私有（Private）两种，是GitHub的核心载体。
- 分支（Branch）：项目的“并行开发线”，默认主分支为 main ，可创建分支开发新功能，避免影响主分支稳定性。
- 提交（Commit）：对代码修改的“快照记录”，每次提交需写清晰说明（Commit Message），便于追溯历史修改。
- Fork：复制他人仓库到自己账户，独立于原仓库，可自由修改，适合基于开源项目二次开发。
- Pull Request（PR）：向原仓库发起“修改合并请求”，原仓库维护者审核通过后，你的修改会被合并到原项目。
- 合并（Merge）：将分支的修改整合到目标分支（如主分支），完成开发后需执行的操作。
- Issues：用于跟踪项目的“问题、需求、任务”，可讨论bug修复、功能建议，是协作沟通的重要工具。

## 二、常用操作步骤

### 1.仓库基础操作

1. 新建仓库：登录GitHub → 点击右上角“+” → 选择“New repository” → 填写仓库名、描述，选择公开/私有 → 点击“Create repository”。
2. 克隆仓库（本地获取远程代码）：打开终端 → 输入 git clone 仓库地址（HTTPS/SSH）  → 回车后自动下载到本地。
3. 提交修改（本地→远程）：

- 本地修改代码后，终端输入 git add . （暂存所有修改）；
- 输入 git commit -m "修改说明（如：修复登录bug）" （提交修改）；
- 输入 git push （推送到远程仓库）。

### 2.分支操作

1.创建并切换分支： git checkout -b 分支名（如：feature/login） ；

2.查看所有分支： git branch （当前分支前有“*”）；

3.切换到主分支： git checkout main ；

4.删除本地分支： git branch -d 分支名 ；

5.推送分支到远程： git push -u origin 分支名 。

### Fork与PR流程

1.Fork他人仓库：打开目标仓库 → 点击右上角“Fork” → 等待复制完成，进入自己账户下的该仓库；

2.克隆自己Fork的仓库到本地，修改代码并提交推送；

3.发起PR：打开自己Fork的仓库 → 点击“Pull request” → 选择原仓库的目标分支和自己的修改分支 → 填写PR说明 → 点击“Create pull request”；

3.等待原仓库维护者审核，根据反馈修改后再次提交即可。

### 4.Issues使用

1.新建Issue：打开仓库 → 点击“Issues” → 点击“New issue” → 选择模板（如bug、需求） → 填写标题和内容 → 点击“Submit new issue”；

2.关闭Issue：问题解决后，在Issue页面点击“Close issue”，或提交代码时在Commit Message中写 Fix #Issue编号 （自动关闭对应Issue）。

## 三、实用技巧

- .gitignore文件：在仓库根目录创建该文件，写入无需提交的文件/文件夹（如 node_modules/ 、 .idea/ ），避免冗余文件上传。
- README.md：仓库的“说明书”，用Markdown编写，介绍项目功能、安装步骤、使用方法，提升项目可读性。
- SSH免密登录：配置SSH密钥后，推送代码无需重复输入账号密码，操作更高效（GitHub官方文档有详细配置步骤）。
- 星标（Star）：收藏感兴趣的仓库，点击仓库右上角“Star”，后续可在自己账户的“Stars”中快速查找。
- Watch：关注仓库动态，仓库更新（如提交、PR、Issue）时会收到通知。

## 四。优秀笔记参考链接

- GitHub 极简教程（https://www.runoob.com/w3cnote/git-guide.html）：以简洁明了的方式讲解 GitHub 核心操作与概念，适合快速梳理知识。
- GitHub 完整入门指南（https://github.com/521xueweihan/git-tips）：包含丰富的 GitHub 操作技巧、实用场景示例，能帮助深入理解 GitHub 各类功能。

