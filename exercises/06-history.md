# Exercise 06：Git 历史管理

## 任务目标

掌握 `log`、`reset` 和 `revert`，理解“移动分支指针”与“用新提交撤销旧提交”的区别。

## 操作要求

请在独立练习分支完成，禁止在共享的 `main` 上练习 `reset`。

1. 从最新 `main` 创建 `practice/<姓名拼音>-history`。
2. 在自己的成员目录创建 `mistake.md`，写入一行任意测试内容。
3. 提交：

   ```bash
   git add GitPractice/members/<自己的目录>/mistake.md
   git commit -m "wrong commit"
   ```

4. 执行 `git log --oneline -5`，记下 `wrong commit` 的提交 ID。
5. 使用安全的共享历史撤销方式创建一个反向提交：

   ```bash
   git revert HEAD
   ```

6. 再次查看日志，确认原提交与 revert 提交都被保留。
7. 在自己的成员目录创建 `history-answer.md`，回答：
   - `git reset` 与 `git revert` 的区别是什么？
   - 已经推送且他人可能使用的提交，为什么通常应选择 `revert`？
   - `git reset --soft`、`--mixed`、`--hard` 对工作区和暂存区有什么不同？
8. 提交答案，提交信息为 `explain reset and revert`。

## 可选本地实验

如需观察 `reset`，请额外创建临时分支并记录提交 ID，再尝试 `git reset --soft HEAD~1` 或 `git reset --mixed HEAD~1`。`--hard` 会丢弃未保存的工作区改动，初学阶段不要在有重要文件的分支上使用。

## 验收方式

- `git log --oneline` 同时包含 `wrong commit` 和对应的 revert 提交。
- `mistake.md` 已被撤销，不存在于当前工作树中。
- `history-answer.md` 的三道问题均已回答，表述准确。
- 能说明为什么不应对已共享历史随意执行 `reset` 后强制推送。
