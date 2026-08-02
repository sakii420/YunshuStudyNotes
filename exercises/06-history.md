# Exercise 06：Git 历史管理

## 任务目标

掌握 `reset`、`revert`、`log` 的使用，理解版本回退的不同方式。

## 操作要求

### 第一部分：制造一个"错误"提交

1. 确保你在自己的个人分支上。

2. 在自己的成员目录下创建 `mistake.md`，内容写：
   ```
   这是一个错误的提交
   ```

3. 提交：
   ```bash
   git add members/<自己的目录>/mistake.md
   git commit -m "wrong commit"
   ```

4. 查看提交记录，记下这个 commit 的 hash：
   ```bash
   git log --oneline
   ```

### 第二部分：用 reset 回退（软回退）

1. 用 `reset --soft` 回退到上一个提交：
   ```bash
   git reset --soft HEAD~1
   ```

2. 查看状态，你会发现 `mistake.md` 还在暂存区：
   ```bash
   git status
   ```

3. 重新提交（相当于修改了上一次提交）：
   ```bash
   git commit -m "fix: correct the mistake"
   ```

### 第三部分：用 revert 撤销提交

1. 再做一个提交，比如在 `mistake.md` 里加一行内容，然后提交：
   ```bash
   git add members/<自己的目录>/mistake.md
   git commit -m "add more content to mistake file"
   ```

2. 用 `revert` 撤销这个提交（会产生一个新的反向提交）：
   ```bash
   git revert HEAD
   ```

3. 查看提交历史，你会看到多了一个 revert 的 commit：
   ```bash
   git log --oneline
   ```

### 第四部分：用 reflog 找回"丢失"的提交

1. 用 `reset --hard` 回退到更早的提交（注意：hard 模式会丢弃工作区修改）：
   ```bash
   git reset --hard HEAD~3
   ```

2. 这时候你会发现刚才的那些提交好像都"丢了"，别慌，用 reflog 找回来：
   ```bash
   git reflog
   ```

3. 找到你想恢复的那个 commit 的 hash，然后 reset 回去：
   ```bash
   git reset --hard <commit-hash>
   ```

## 思考题

在自己的成员目录下创建 `history-answer.md`，回答以下问题：
1. `reset` 和 `revert` 有什么区别？
2. `reset` 的三种模式（soft、mixed、hard）分别有什么不同？
3. 什么时候应该用 `reset`，什么时候应该用 `revert`？

## 验收方式

- 能演示 reset 和 revert 的使用。
- 能解释 reset 和 revert 的区别。
- 会用 reflog 找回误删的提交。
- `history-answer.md` 中包含三个问题的回答。
