# Exercise 02：分支管理

## 任务目标

掌握 `branch`、`switch`、`checkout` 的使用，理解分支的概念和作用。

## 操作要求

1. 查看当前所有分支：
   ```bash
   git branch -a
   ```

2. 创建个人分支，命名格式：`feature/名字拼音`
   例如：
   ```bash
   git switch -c feature/hu_han
   ```

3. 确认已切换到新分支：
   ```bash
   git branch
   ```

4. 在自己的成员目录下新增 `branch.md` 文件，内容写：
   - 你创建的分支名
   - 你对分支的理解（一句话）

5. 提交修改：
   ```bash
   git add members/<自己的目录>/branch.md
   git commit -m "create personal branch"
   ```

6. 推送到远程仓库：
   ```bash
   git push -u origin feature/<你的名字>
   ```

## 验收方式

- 本地存在以 `feature/` 开头的个人分支。
- 个人目录下有 `branch.md` 文件。
- 最新 commit message 为 `create personal branch`。
- GitHub 上能看到对应的远程分支。
