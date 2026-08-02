# Exercise 03：Merge 合并

## 任务目标

掌握 `merge` 的使用，理解 fast-forward 和 merge commit 的区别。

## 操作要求

### 第一部分：fast-forward 合并

1. 确保你在 main 分支上：
   ```bash
   git switch main
   ```

2. 创建一个新分支 `ff-demo`：
   ```bash
   git switch -c ff-demo
   ```

3. 在自己的成员目录下创建 `merge-ff.md`，写一句话，然后提交：
   ```bash
   git add members/<自己的目录>/merge-ff.md
   git commit -m "add fast forward demo file"
   ```

4. 切回 main 分支，进行合并：
   ```bash
   git switch main
   git merge ff-demo
   ```

5. 观察合并结果，这是 fast-forward 合并（没有产生新的 commit）。

### 第二部分：merge commit 合并

1. 在 main 分支上，在自己的成员目录下创建 `merge-main.md`，写一句话，提交：
   ```bash
   git add members/<自己的目录>/merge-main.md
   git commit -m "add file on main branch"
   ```

2. 创建一个新分支 `mc-demo`：
   ```bash
   git switch -c mc-demo
   ```

3. 在自己的成员目录下创建 `merge-branch.md`，写一句话，提交：
   ```bash
   git add members/<自己的目录>/merge-branch.md
   git commit -m "add file on feature branch"
   ```

4. 切回 main 分支，进行合并：
   ```bash
   git switch main
   git merge mc-demo
   ```

5. 观察合并结果，这次产生了一个新的 merge commit。

### 第三部分：查看合并历史

1. 用图形化方式查看提交历史：
   ```bash
   git log --graph --all --oneline
   ```

2. 截图保存到自己的成员目录，命名为 `merge-graph.png`（可选）。

## 验收方式

- 能解释 fast-forward 和 merge commit 的区别。
- `git log --graph --all` 能看到完整的合并历史。
- 三个 demo 文件都存在于 main 分支。
