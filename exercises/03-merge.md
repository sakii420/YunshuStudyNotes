# Exercise 03：Merge 合并

## 任务目标

掌握 `merge`，能识别 fast-forward 与 merge commit，并能用图形化日志检查合并历史。

## 操作要求

本练习先在本地练习分支上演示两种合并，不直接推送 `main`。

### A. Fast-forward 合并

1. 从当前个人分支创建实验基线分支：

   ```bash
   git switch -c practice/<姓名拼音>-merge
   git switch -c practice/<姓名拼音>-ff
   ```

2. 在自己的 `branch.md` 末尾增加一段“fast-forward 实验”，提交为 `practice fast forward merge`。
3. 回到基线分支并合并：

   ```bash
   git switch practice/<姓名拼音>-merge
   git merge practice/<姓名拼音>-ff
   ```

4. 观察输出中是否出现 `Fast-forward`。

### B. Merge commit 合并

1. 从实验基线创建新分支：

   ```bash
   git switch -c practice/<姓名拼音>-merge-commit
   ```

2. 在自己的 `branch.md` 增加一段“merge commit 实验”，提交为 `practice merge commit`。
3. 回到实验基线，先在自己的 `profile.md` 增加一行内容并提交为 `update profile before merge`，使两个分支产生不同提交。
4. 合并并保留合并提交：

   ```bash
   git merge --no-ff practice/<姓名拼音>-merge-commit -m "merge personal practice branch"
   ```

## 验收方式

执行：

```bash
git log --graph --all --oneline --decorate
```

验收时应能指出：

- 哪一次合并是 fast-forward。
- 哪一个节点是 merge commit，且该节点有两个父提交。
- 为什么 `--no-ff` 会保留分支合并节点。

完成实验后，将需要保留的学习成果通过个人功能分支和 Pull Request 交给组长审核；不要直接推送 `main`。
