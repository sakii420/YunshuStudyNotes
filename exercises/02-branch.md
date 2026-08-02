# Exercise 02：分支管理

## 任务目标

掌握 `branch`、`switch` 和 `checkout`，理解分支是指向提交的可移动指针。

## 操作要求

1. 切换到最新的 `main`：

   ```bash
   git switch main
   git pull --ff-only origin main
   ```

2. 创建并切换到个人分支，分支格式为 `feature/name`：

   ```bash
   git switch -c feature/<姓名拼音>
   ```

   旧版 Git 可使用等价命令 `git checkout -b feature/<姓名拼音>`，两种方式任选一种。

3. 使用 `git branch --show-current` 确认当前分支。
4. 在自己的成员目录新增 `branch.md`，记录：当前分支名、创建分支所用命令、`switch` 与 `checkout` 的区别。
5. 暂存并提交，提交信息必须为：

   ```text
   create personal branch
   ```

## 验收方式

- `git branch --show-current` 输出正确的个人分支名。
- `branch.md` 位于自己的成员目录，并回答了三项内容。
- `git log -1 --oneline` 显示提交信息 `create personal branch`。
- 执行 `git branch --contains HEAD` 能看到当前个人分支。

## 常见问题

- 如果提示分支已经存在，使用 `git switch feature/<姓名拼音>`，不要重复创建。
- 如果工作区有未提交改动，先确认改动归属并提交，不要随意丢弃。
