
# Git 使用指南

## 目录

- 初始化项目
- 添加与提交
- 分支管理
- 远程仓库操作
- 推送与拉取
- 合并与变基
- 查看与比较
- 撤销与回滚
- 标签管理
- 提交ID与短ID说明

---

## 初始化项目

- 初始化一个新的本地仓库：
  ```bash
  git init
  ```

---

## 添加与提交

- 查看当前状态：
  ```bash
  git status
  ```

- 将文件添加到暂存区：
  ```bash
  git add 文件名
  git add .   # 添加所有变化
  ```

- 提交暂存区到本地仓库：
  ```bash
  git commit -m "提交说明"
  ```

- 修改最近一次提交信息：
  ```bash
  git commit --amend
  ```

- 快速添加并提交（改过的文件）：
  ```bash
  git commit -am "提交说明"
  ```

---

## 分支管理

- 查看本地分支：
  ```bash
  git branch
  ```

- 创建新分支：
  ```bash
  git branch 分支名
  ```

- 切换到其他分支：
  ```bash
  git checkout 分支名
  ```

- 创建并切换新分支：
  ```bash
  git checkout -b 分支名
  ```

- 删除本地分支：
  ```bash
  git branch -d 分支名
  ```
  （未合并时使用 `-D` 强制删除）

---

## 远程仓库操作

- 添加远程仓库：
  ```bash
  git remote add origin 仓库地址
  ```

- 查看远程仓库信息：
  ```bash
  git remote -v
  ```

- 删除远程仓库：
  ```bash
  git remote remove origin
  ```

---

## 推送与拉取

- 推送本地分支到远程：
  ```bash
  git push origin 分支名
  ```

- 强制推送（常用于rebase之后）：
  ```bash
  git push origin 分支名 --force
  ```

- 拉取远程分支并自动合并：
  ```bash
  git pull origin 分支名
  ```

- 只下载远程更新（不合并）：
  ```bash
  git fetch origin
  ```

---

## 合并与变基

- 合并其他分支到当前分支：
  ```bash
  git merge 分支名
  ```

- 使用 rebase 让提交历史更清晰：
  ```bash
  git rebase 分支名
  ```

- 中止正在进行的 rebase：
  ```bash
  git rebase --abort
  ```

- 解决冲突后继续 rebase：
  ```bash
  git rebase --continue
  ```

---

## 查看与比较

- 查看提交历史：
  ```bash
  git log
  ```

- 简洁查看提交历史：
  ```bash
  git log --oneline
  ```

- 查看某文件的提交记录：
  ```bash
  git log 文件名
  ```

- 查看未提交的本地变化：
  ```bash
  git diff
  ```

- 比较两个版本（提交）之间的差异：
  ```bash
  git diff 版本A 版本B
  ```

- 比较两个版本中某个特定文件的变化：
  ```bash
  git diff 版本A 版本B -- 文件名
  ```

---

## 撤销与回滚

- 撤销最近一次提交（保留改动）：
  ```bash
  git reset --soft HEAD~1
  ```

- 强制回到某个版本（慎用）：
  ```bash
  git reset --hard 提交ID
  ```

- 生成一个反向提交来撤销某次提交：
  ```bash
  git revert 提交ID
  ```

- 取消文件的暂存状态（撤回 add）：
  ```bash
  git reset HEAD 文件名
  ```

- 恢复修改的文件到上一次提交的状态：
  ```bash
  git checkout -- 文件名
  ```

---

## 标签管理

- 给当前提交打标签：
  ```bash
  git tag 标签名
  ```

- 查看所有标签：
  ```bash
  git tag
  ```

- 删除本地标签：
  ```bash
  git tag -d 标签名
  ```

- 推送标签到远程仓库：
  ```bash
  git push origin 标签名
  ```

- 删除远程仓库中的标签：
  ```bash
  git push origin :refs/tags/标签名
  ```

---

## 提交ID与短ID说明

- 每次 `git commit` 后，Git 会生成一个唯一的提交ID（commit ID），通常是 40 位的哈希值。
- 例如：
  ```
  a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6q7r8s9t
  ```
- 在日常使用中，只要提交ID的前几位能够唯一标识，就可以使用短ID，例如：
  ```
  a1b2c3d
  ```
- 无论是完整ID还是短ID，本质上指向的是同一个提交版本。

---

# 附录：常见 Git 流程

1. 新建本地仓库
   ```bash
   git init
   ```

2. 编辑文件，保存后添加到暂存区
   ```bash
   git add .
   ```

3. 提交到本地仓库
   ```bash
   git commit -m "提交说明"
   ```

4. 添加远程仓库
   ```bash
   git remote add origin 仓库地址
   ```

5. 推送到远程
   ```bash
   git push origin main
   ```

6. 拉取远程仓库更新
   ```bash
   git pull origin main
   ```

7. 分支开发
   ```bash
   git checkout -b 分支名
   ```

8. 合并开发结果
   ```bash
   git checkout main
   git merge 分支名
   ```

---

# 说明

本指南适用于日常开发中使用 Git 的常见场景，涵盖基础使用、分支管理、远程同步、冲突处理、撤销回滚、标签管理等内容。
