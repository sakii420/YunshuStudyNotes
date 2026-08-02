# Git 学习训练

本模块用于检验小组成员的 Git 基础操作与协作能力。请按顺序完成 `exercises/` 中的 6 个练习，并将练习成果保存在自己的成员目录中。

## 参与成员

| 姓名 | 角色 | 成员目录 | 个人分支 |
| --- | --- | --- | --- |
| 胡瀚 | 组长 / 仓库管理员 | `members/hu_han/` | `feature/hu_han` |
| 王睿轩 | 成员 | `members/wang_ruixuan/` | `feature/wang_ruixuan` |
| 杜振羽 | 成员 | `members/du_zhenyu/` | `feature/du_zhenyu` |

## 训练流程

1. 克隆仓库，并进入仓库目录。
2. 阅读当前练习的任务说明。
3. 从最新的 `main` 创建个人分支。
4. 只在自己的成员目录中完成任务（冲突练习除外）。
5. 按题目要求创建 commit。
6. 将个人分支推送到 GitHub。
7. 创建 Pull Request，由组长检查并合并。

## 推荐顺序

1. [基础操作](exercises/01-basic.md)
2. [分支管理](exercises/02-branch.md)
3. [Merge 合并](exercises/03-merge.md)
4. [冲突解决](exercises/04-conflict.md)
5. [远程协作](exercises/05-remote.md)
6. [Git 历史管理](exercises/06-history.md)

## 协作规则

- 只能修改自己的 `members/姓名拼音/` 目录，题目明确指定的公共文件除外。
- 禁止修改其他成员的目录。
- 禁止直接执行 `git push origin main`。
- 开始新任务前先更新本地 `main`，再创建任务分支。
- 提交前使用 `git status` 和 `git diff --staged` 检查改动。
- 一个 commit 只完成一个清晰目标，提交信息使用题目指定内容。

标准工作流示例：

```bash
git switch main
git pull --ff-only origin main
git switch -c feature/name
# 完成任务后
git add <本题文件>
git diff --staged
git commit -m "题目指定的提交信息"
git push -u origin feature/name
```

## 完成标准

- 6 个练习均有可检查的文件或 Git 历史证据。
- 个人分支已推送，Pull Request 信息完整。
- 能解释自己执行的关键命令，而不是只复制命令。
- 总分按 [评分标准](check/grading.md) 计算，满分 100 分。
