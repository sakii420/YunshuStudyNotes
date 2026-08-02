# Exercise 00：前置准备 - 绑定远程仓库

## 任务目标

完成 Git 环境配置，学会给本地仓库绑定远程仓库，为后续练习做准备。

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

### 第三步：创建本地仓库

1. 在你电脑上找个地方，新建一个文件夹，名字随便取（比如 `YunshuStudyNotes`）
2. 进入这个文件夹，右键打开 Git Bash（或者用命令行 cd 进去）
3. 初始化本地仓库：
   ```bash
   git init
   ```

### 第四步：绑定远程仓库（重点）

给你刚创建的本地仓库，绑定远程仓库地址：

```bash
git remote add origin https://github.com/sakii420/YunshuStudyNotes.git
```

- `origin` 是远程仓库的别名（默认都叫 origin，你也可以改成别的）
- 后面的 URL 就是远程仓库的 HTTPS 地址

验证是否绑定成功：
```bash
git remote -v
```

能看到两行输出（fetch 和 push）就说明绑定成功了：
```
origin  https://github.com/sakii420/YunshuStudyNotes.git (fetch)
origin  https://github.com/sakii420/YunshuStudyNotes.git (push)
```

### 第五步：拉取远程仓库代码

绑定好之后，把远程仓库的内容拉到本地：

```bash
git pull origin main
```

> 如果你的远程默认分支叫 master，就把 main 改成 master。

拉完之后用 `ls` 或 `dir` 看看，远程仓库的文件就都到本地了。

### 第六步：查看当前状态

```bash
git status
```

看到 `On branch main` 之类的提示就 OK 了。

---

## 补充：其他 remote 常用命令

| 命令 | 作用 |
|------|------|
| `git remote -v` | 查看当前绑定的远程仓库 |
| `git remote add <别名> <地址>` | 添加远程仓库 |
| `git remote remove <别名>` | 删除远程仓库 |
| `git remote rename <旧名> <新名>` | 重命名远程仓库 |
| `git remote set-url <别名> <新地址>` | 修改远程仓库地址 |

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

5. 把远程地址改成 SSH 方式：
   ```bash
   git remote set-url origin git@github.com:sakii420/YunshuStudyNotes.git
   ```

## 验收方式

- 能成功初始化本地仓库
- 能用 `git remote add` 绑定远程仓库
- `git remote -v` 能看到正确的远程地址
- 能成功 pull 远程仓库的代码

---

## 常见问题

### Q：pull 的时候超时/连不上怎么办？
A：国内访问 GitHub 经常抽风，可以：
1. 多试几次
2. 配置代理
3. 用手机热点试试

### Q：我之前已经 clone 过仓库了，还要再 remote add 吗？
A：不用。clone 下来的仓库已经自动绑定好远程了，直接用就行。

### Q：push 的时候提示认证失败怎么办？
A：现在 GitHub 不支持用密码 push 了，需要用 Personal Access Token：
1. 去 GitHub → Settings → Developer settings → Personal access tokens
2. 生成一个新的 token，勾选 repo 权限
3. push 的时候用户名填 GitHub 用户名，密码填这个 token

### Q：我绑错了远程地址怎么办？
A：用 `git remote set-url origin 新地址` 修改，或者先 `git remote remove origin` 删掉再重新 add。
