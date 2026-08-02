# Exercise 05：远程协作与 Pull Request

## 任务目标

掌握 `remote`、`pull`、`push` 的使用，熟悉 Pull Request 工作流。

## 操作要求

1. 创建一个新的 feature 分支：
   ```bash
   git switch -c feature/<你的名字>-pr
   ```

2. 修改仓库根目录的 `README.md`，在末尾加上一行：
   ```
   - <你的名字>：已完成 Git 基础学习
   ```

3. 提交修改：
   ```bash
   git add README.md
   git commit -m "add my name to contributors list"
   ```

4. 推送到远程仓库：
   ```bash
   git push -u origin feature/<你的名字>-pr
   ```

5. 在 GitHub 网页上创建 Pull Request：
   - 标题格式：`Git Practice: <你的名字>`
   - 正文包含以下内容：
     ```
     ## 完成内容
     - （列出你完成的练习）
     
     ## 遇到的问题
     - （列出你遇到的问题，没有就写"无"）
     
     ## 解决方式
     - （你是怎么解决这些问题的）
     ```

6. 等待组长审核，根据反馈修改（如果有的话），修改后直接 push 到同一个分支，PR 会自动更新。

## 验收方式

- 成功创建 Pull Request，标题格式正确。
- PR 正文包含要求的三个部分。
- 组长审核通过后，PR 成功合并到 main。
- 合并后本地 main 分支同步最新代码：
  ```bash
  git switch main
  git pull
  ```
