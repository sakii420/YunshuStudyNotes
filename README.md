# Git 学习训练

本模块用于检验小组成员 Git 使用能力。

## 训练流程

阅读exercises目录下的任务，逐个完成。

## 目录结构

```
├── README.md          # 本说明文件
├── exercises/         # 练习题目录
│   ├── 01-basic.md    # 基础操作
│   ├── 02-branch.md   # 分支管理
│   ├── 03-merge.md    # 合并操作
│   ├── 04-conflict.md # 冲突解决
│   ├── 05-remote.md   # 远程协作
│   └── 06-history.md  # 历史管理
├── members/           # 成员提交区域
│   ├── hu_han/        # 胡瀚
│   ├── wang_ruixuan/  # 王睿轩
│   └── du_zhenyu/     # 杜振羽
└── check/             # 验收说明
    └── grading.md     # 评分标准
```

## 成员目录规范

每个人只能修改 `members/自己的名字/` 目录下的文件：
- 胡瀚：`members/hu_han/`
- 王睿轩：`members/wang_ruixuan/`
- 杜振羽：`members/du_zhenyu/`

**禁止：**
- 修改其他成员目录
- 直接 push 到 main 分支

## Git 工作流要求

所有成员必须遵守：

**禁止直接 push main：**
```bash
git push origin main  # ❌ 不允许
```

**正确流程：**
```bash
git switch -c feature/name   # 创建个人分支
# 完成任务
git add .
git commit -m "xxx"
git push origin feature/name # 推送到个人分支
# 然后创建 Pull Request
```

- <hu_han>：已完成 Git 基础学习
- <du_zhenyu>:已完成Git基础学习
