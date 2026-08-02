# Git 训练评分标准

| 项目 | 分值 | 评分要点 |
| --- | --- | --- |
| clone/add/commit 基础操作 | 20 | - 能正确克隆仓库<br>- 能正确使用 add 和 commit<br>- commit message 规范清晰 |
| branch 使用 | 20 | - 能正确创建和切换分支<br>- 分支命名规范<br>- 理解分支的概念和作用 |
| merge 操作 | 15 | - 能正确执行合并操作<br>- 理解 fast-forward 和 merge commit 的区别<br>- 能查看合并历史 |
| 冲突解决 | 20 | - 理解冲突产生的原因<br>- 能正确手动解决冲突<br>- 解决后代码/内容正常 |
| 远程协作 | 15 | - 能正确 push 和 pull<br>- 能创建 Pull Request<br>- PR 格式规范，内容完整 |
| commit 规范 | 10 | - commit message 清晰有意义<br>- 小步提交，一个功能一个 commit<br>- 不提交无关文件 |

**总分：100 分**

## 加分项（额外 10 分）

- 能熟练使用 `reflog` 找回误删的提交（+3）
- 能解释 `reset` 三种模式的区别（+3）
- 能使用 `rebase` 整理提交历史（+4）

## 扣分项

- 直接 push 到 main 分支（-20）
- 修改其他成员目录的文件（-10）
- commit message 完全看不懂（-5）
- 提交了大量无关文件（-5）
