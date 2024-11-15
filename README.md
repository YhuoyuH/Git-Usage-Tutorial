# Git使用教程

## 1. 由远端获取仓库文件

### 1.1 拉取Git仓库

在本地选好一个位置合适的文件夹，利用`git clone`将远端仓库拉取到本地，这样本地的项目就会和你远端的仓库建立连接。

不过在此之前要在`Git Bash`中登陆上自己的`GitHub`账户

```bash
git clone "Your repository's url"
```

![](https://imgur.com/si55Kxj.jpg)

### 1.2 更新仓库文件

将你想要上传的文件放入拉取仓库的文件夹下，也可以选择在本地修改仓库中的文件

### 1.3 同步远端仓库文件

#### 1.3.1 初始化git

```bash
git init
```

#### 1.3.2 将文件添加到暂存区

利用下面的命令将指定文件添加到`git`暂存区

```bash
git add filename1，filename2
```

如果想要同步所有的文件，运行下列命令

```bash
git add .
```

#### 1.3.3 更改仓库文件

利用下面命令将暂存区的文件上传到仓库中

```bash
git commit -m "你要提交的信息"
```

当然，你也可以选择不用`git add `命令而直接使用`git commit`

```bash
git commit -a -m "Commit message"
```

这个命令的作用是自动把所有已跟踪的修改和删除的文件添加到暂存区并提交，但不包括新文件。

#### 1.3.4 上传文件

利用下面命令对远端仓库进行修改

```bash
git push
```

## 2.由本地创建仓库文件

如果你在 GitHub 上创建了一个仓库，通常的步骤如下：

### 1.**创建仓库**

- 登录 GitHub 账户。
- 点击右上角的“+”号，选择“New repository”。
- 给仓库起个名字，选择是公开（public）还是私有（private），然后点击“Create repository”。

### 2.**初始化本地仓库**

- 在本地机器上创建一个新的文件夹，或者在现有项目的文件夹中。
- 打开命令行（终端），然后进入到你的文件夹。

### 3.**将本地仓库与 GitHub 仓库关联**

- 在本地文件夹中运行以下命令初始化 Git 仓库：
  ```bash
  git init
  ```
- 添加远程 GitHub 仓库作为 origin：
  ```bash
  git remote add origin https://github.com/your-username/your-repository-name.git
  ```

### 4.**添加文件并提交**

- 使用 `git add` 命令将文件添加到暂存区：
  ```bash
  git add .
  ```
- 使用 `git commit` 提交文件：
  ```bash
  git commit -m "Initial commit"
  ```

### 5.**推送到 GitHub**

- 使用 `git push` 将本地仓库推送到 GitHub 上：
  ```bash
  git push -u origin master
  ```
- 如果是首次推送，并且你设置了 GitHub 仓库的默认分支为 `main`，你可以用 `main` 替换 `master`。

## 3.删除仓库中的文件

### 1. **删除本地文件**
首先，在本地项目中删除该文件。你可以直接在文件管理器中删除它，或者使用命令行删除：

```bash
rm path/to/your/file
```

### 2. **在 Git 中标记文件删除**
删除文件后，你需要告诉 Git 你已经删除了这个文件，并将变更提交到版本控制中。

```bash
git rm path/to/your/file
```

### 3. **提交变更**
然后提交这个删除操作：

```bash
git commit -m "Remove unnecessary file"
```

### 4. **推送更改到 GitHub**
提交完成后，推送更改到 GitHub：

```bash
git push origin main
```

> 注意：如果你的仓库默认分支是 `master`，而不是 `main`，需要将 `main` 替换为 `master`。

### 5. **从 GitHub 上删除文件**
文件会从 GitHub 上同步删除。刷新 GitHub 页面后，你会发现该文件已经被删除。
