# GitHub 进阶笔记

## 一、版本回溯与提交修正

- 撤销本地未推送提交： git reset --soft HEAD~n （n=撤销次数，保留代码）； --hard  会删除更改（慎用）
- 修正最近一次提交： git commit --amend （未推送时，可改信息/补文件）
- 恢复已删分支： git reflog  找最后提交 SHA 值 →  git checkout -b 分支名 SHA值  重建

## 二、协作权限与分支保护

1. 权限分配

- 个人仓库：Settings → Collaborators and teams，分配 Write/Maintain 等角色
- 组织级：创建 Organization → 按项目分组仓库 → Teams 批量分配权限

2. 主分支保护

- 路径：Settings → Branch protection rules
- 核心规则：PR 需审查通过、CI 测试通过方可合并，禁止直接推送主分支

## 三、本地自动化（Git Hooks）

- 原生配置：.git/hooks 目录下新建  pre-commit  脚本（如代码格式化、lint 检查），需加执行权限  chmod +x 
- 简化工具：用  husky  管理 hooks，支持团队共享配置，无需直接操作 .git 目录

## 四、子模块管理（大型项目依赖）

- 引入子模块： git submodule add 仓库地址 子模块目录 
- 初始化子模块： git submodule init && git submodule update 
- 克隆含子模块项目： git clone --recursive 项目地址 
- 更新子模块： git submodule update --remote 

## 五、GitHub Actions（CI/CD 进阶）

1. 多阶段工作流

yaml

jobs:
  build:  # 构建阶段
    runs-on: ubuntu-latest
    steps: [执行构建命令]
  test:   # 测试阶段（依赖构建）
    needs: build
    runs-on: ubuntu-latest
    steps: [执行测试命令]
  deploy: # 部署阶段（依赖测试）
    needs: test
    runs-on: ubuntu-latest
    steps: [执行部署命令]


2. 实用配置

- 缓存依赖：用  actions/cache  缓存 node_modules/pip 依赖，加速运行
- 敏感信息：Settings → Secrets and variables 新增密钥，Actions 中用  secrets.密钥名  引用

## 六、问题排查与性能优化

- 查找大文件： git rev-list --objects --all | grep "$(git verify-pack -v .git/objects/pack/*.idx | sort -k 3 -n | tail -1 | awk '{print $1}')" 
- 清理大文件：用  BFG Repo-Cleaner  工具（需提前备份仓库）
- 加速克隆： git clone --depth 1 仓库地址 （浅克隆，仅拉取最新版本）

参考链接：[笔记](https://blog.csdn.net/weixin_70682362/article/details/144204436)