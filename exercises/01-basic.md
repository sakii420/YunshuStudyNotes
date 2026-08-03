# Exercise 01：Git 基础操作

## 任务目标

掌握 `clone`、`status`、`add`、`commit`、`push` 和 `log` 的基本用法，理解工作区、暂存区和本地仓库之间的关系。

## 操作要求

1. 使用 `git clone <仓库地址>` 克隆仓库；如果已经克隆，可从第 2 步开始。

2. 进入仓库，执行 `git status`，确认当前状态。

3. 在 `members/自己的名字/` 目录下创建 `profile.md`，写一段自我介绍。

4. 只暂存本题文件，不要使用 `git add .` 应当：
   ```bash
   git add members/<自己的目录>/profile.md
   ```

5. 查看暂存内容，然后提交：
   ```bash
   git diff --staged
   git commit -m "add personal git profile"
   ```

6. 查看最近的提交记录，并在个人分支上推送：
   ```bash
   git log --oneline
   git push -u origin <当前分支名>
   ```

## 验收方式

- `profile.md` 位于正确的个人目录，且包含要求的三项内容。
- `git status` 显示本题改动已提交。
- `git log --oneline` 的最新提交信息为 `add personal git profile`。
- GitHub 上能看到该个人分支和对应文件。
