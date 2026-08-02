# Exercise 04：冲突解决

## 任务目标

掌握冲突（conflict）的产生原因和解决方法。

## 准备工作

组长需要先在 main 分支的 `conflict.txt` 中写入初始内容：
```
Git is powerful.
```

## 操作要求（两人一组完成）

### 第一步：制造冲突

1. **成员 A（王睿轩）**：
   - 创建自己的分支
   - 修改 `conflict.txt` 第一行为：`Git is easy.`
   - 提交并推送到远程
   - 提 PR 合并到 main（先合并这个）

2. **成员 B（杜振羽）**：
   - 创建自己的分支（基于合并前的 main）
   - 修改 `conflict.txt` 第一行为：`Git is difficult.`
   - 提交并推送到远程
   - 提 PR 合并到 main（这个会产生冲突）

### 第二步：解决冲突

1. 成员 B 在本地拉取最新的 main：
   ```bash
   git switch main
   git pull
   ```

2. 切回自己的分支，合并 main：
   ```bash
   git switch feature/<你的名字>
   git merge main
   ```

3. 此时会提示冲突，打开 `conflict.txt`，你会看到类似这样的内容：
   ```
   <<<<<<< HEAD
   Git is difficult.
   =======
   Git is easy.
   >>>>>>> main
   ```

4. 手动解决冲突（保留你认为合适的内容，或者合并成一句话），删除 `<<<<<<<`、`=======`、`>>>>>>>` 这些标记。

5. 提交解决后的结果：
   ```bash
   git add conflict.txt
   git commit -m "resolve merge conflict"
   ```

6. 推送到远程，再看 PR 应该就可以合并了。

## 验收方式

- 能说清楚冲突是怎么产生的。
- `conflict.txt` 最终内容合理，没有冲突标记。
- 最新 commit message 为 `resolve merge conflict`。
- PR 能够成功合并到 main。
