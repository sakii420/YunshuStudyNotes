# Exercise 04：冲突解决

## 任务目标

认识冲突标记，掌握 `status`、手动编辑、`add` 和 `commit` 组成的冲突解决流程。

## 准备

公共文件 `GitPractice/conflict.txt` 的初始内容为：

```text
Git is powerful.
```

本练习由王睿轩和杜振羽协作完成。开始前，两人都必须从同一个最新 `main` 提交创建各自分支。

## 分工

- 王睿轩在 `feature/wang_ruixuan-conflict` 中将该行改为 `Git is easy.`，提交信息为 `describe git as easy`。
- 杜振羽在 `feature/du_zhenyu-conflict` 中将该行改为 `Git is difficult.`，提交信息为 `describe git as difficult`。

两人分别推送分支。组长先将其中一个分支合并到用于验收的练习分支，再合并另一个分支，从而触发冲突。不要为制造冲突直接改动或推送远程 `main`。

## 冲突解决步骤

1. 执行 `git status`，确认冲突文件。
2. 打开 `conflict.txt`，找到以下标记并理解两侧内容：

   ```text
   <<<<<<<
   =======
   >>>>>>>
   ```

3. 协商最终语句，删除全部冲突标记，保证文件只保留一条完整、合理的英文句子。
4. 标记为已解决并提交：

   ```bash
   git add GitPractice/conflict.txt
   git commit -m "resolve merge conflict"
   ```

如果需要放弃本次尚未完成的合并，可使用 `git merge --abort` 回到合并前状态。

## 验收方式

- 合并过程中确实出现冲突，`git status` 曾显示 `both modified`。
- 文件中不存在 `<<<<<<<`、`=======`、`>>>>>>>`。
- 解决冲突的提交信息为 `resolve merge conflict`。
- `git log --graph --all --oneline` 能展示两条修改历史及最终合并结果。
- 两位成员都能说明最终内容为何这样选择。
