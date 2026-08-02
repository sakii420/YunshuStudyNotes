# Exercise 00：前置准备 - 连接仓库

## 任务目标

完成 Git 环境配置，成功连接到远程仓库，为后续练习做准备。

## 操作要求

### 第一步：安装 Git

1. 下载 Git：https://git-scm.com/downloads
2. 安装时一路下一步就行，默认选项都没问题
3. 安装完成后，打开终端（Git Bash / cmd / PowerShell），输入：
   ```bash
   git --version
   ```
   能看到版本号就说明安装成功了。

### 第二步：配置用户名和邮箱

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱@example.com"
```

> 注意：这里的名字和邮箱最好和你 GitHub 账号的一致，这样提交记录才能正确关联到你的 GitHub 账号。

验证配置：
```bash
git config --list
```

### 第三步：克隆仓库（HTTPS 方式）

直接用 HTTPS 方式克隆仓库，最简单直接：

```bash
git clone https://github.com/sakii420/YunshuStudyNotes.git
```

> 第一次 push 的时候会提示输入 GitHub 用户名和密码（现在密码要用 Personal Access Token，不是登录密码）。
>
> Windows 用户推荐安装 **Git Credential Manager**（安装 Git 时默认带的），这样只需要输一次，以后就不用再输了。

### 第四步：进入仓库目录

```bash
cd YunshuStudyNotes
```

查看当前状态：
```bash
git status
```

看到 `On branch main` 之类的提示就 OK 了。

---

## 进阶：配置 SSH 免密登录（可选）

如果你觉得每次 push 都要输密码麻烦，可以配置 SSH 密钥，配置一次以后都不用输密码了。

1. 生成 SSH 密钥：
   ```bash
   ssh-keygen -t ed25519 -C "你的邮箱@example.com"
   ```
   一路回车就行，默认路径、不用设密码。

2. 查看公钥：
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   复制输出的全部内容（从 `ssh-ed25519` 开始到你的邮箱结束）。

3. 把公钥添加到 GitHub：
   - 打开 GitHub → 右上角头像 → Settings
   - 左边选 SSH and GPG keys
   - 点 New SSH key
   - Title 随便写（比如"我的电脑"）
   - Key 粘贴刚才复制的公钥
   - 点 Add SSH key

4. 测试连接：
   ```bash
   ssh -T git@github.com
   ```
   看到 `Hi xxx! You've successfully authenticated...` 就说明连接成功了。

5. 用 SSH 方式克隆仓库：
   ```bash
   git clone git@github.com:sakii420/YunshuStudyNotes.git
   ```

## 验收方式

- 能成功克隆仓库到本地
- 能看到仓库里的文件
- `git status` 命令能正常执行

---

## 常见问题

### Q：clone 的时候超时/连不上怎么办？
A：国内访问 GitHub 经常抽风，可以：
1. 多试几次
2. 配置代理
3. 用手机热点试试

### Q：我之前已经配置过 Git 了，还要再配吗？
A：不用，直接从第三步克隆仓库开始就行。

### Q：push 的时候提示认证失败怎么办？
A：现在 GitHub 不支持用密码 push 了，需要用 Personal Access Token：
1. 去 GitHub → Settings → Developer settings → Personal access tokens
2. 生成一个新的 token，勾选 repo 权限
3. push 的时候用户名填 GitHub 用户名，密码填这个 token
