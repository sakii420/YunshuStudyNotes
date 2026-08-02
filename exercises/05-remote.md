# Exercise 05：远程协作

## 任务目标

掌握 `remote`、`pull`、`push` 和 Pull Request 工作流，理解本地分支与远程跟踪分支的关系。

## 操作要求

1. 查看远程仓库配置：

   ```bash
   git remote -v
   ```

2. 获取并更新 `main`，然后创建本题功能分支：

   ```bash
   git switch main
   git pull --ff-only origin main
   git switch -c feature/<姓名拼音>-remote
   ```

3. 在自己的 `profile.md` 中新增“Git 学习进度”小节。
4. 提交改动，并将功能分支推送到 GitHub：

   ```bash
   git push -u origin feature/<姓名拼音>-remote
   ```

5. 在 GitHub 创建 Pull Request，请求合并到 `main`。不要直接执行 `git push origin main`。

## Pull Request 要求

标题格式：

```text
Git Practice: name
```

正文必须包含：

```markdown
## 完成内容

## 遇到的问题

## 解决方式
```

如果没有遇到问题，也要写明“暂未遇到问题”，不能留空。

## 验收方式

- `git remote -v` 中的 fetch 与 push 地址正确。
- GitHub 上存在本题远程分支。
- Pull Request 的目标分支是 `main`，标题与正文格式符合要求。
- Pull Request 只包含本人的练习改动，没有其他成员文件或无关文件。
- 组长完成审核后再合并。
