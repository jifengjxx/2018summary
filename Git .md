>  参考文献：
>
> 1. [Git 菜鸟教程](http://www.runoob.com/git/git-tutorial.html)
> 2. [Git 简易指南](http://www.bootcss.com/p/git-guide/)
> 3. [Git 命令手册](https://git-scm.com/docs)
> 4. [Git 命令手册(pdf版)](http://www.runoob.com/manual/github-git-cheat-sheet.pdf)
> 5. [Git 教程：廖雪峰](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/)

# # Git 概述

## 1、Git 

Git是一个开源的 **分布式版本控制系统**，用于敏捷高效地处理任何或小或大的项目。

## 2、Git 诞生

Linus在1991年创建了开源的Linux，从此，Linux系统不断发展，已经成为最大的服务器系统软件了。

Linus虽然创建了Linux，但Linux的壮大是靠全世界热心的志愿者参与的，这么多人在世界各地为Linux编写代码，那Linux的代码是如何管理的呢？

事实是，在2002年以前，世界各地的志愿者把源代码文件通过diff的方式发给Linus，然后由Linus本人通过手工方式合并代码！

你也许会想，为什么Linus不把Linux代码放到版本控制系统里呢？不是有CVS、SVN这些免费的版本控制系统吗？因为Linus坚定地反对CVS和SVN，这些集中式的版本控制系统不但速度慢，而且必须联网才能使用。有一些商用的版本控制系统，虽然比CVS、SVN好用，但那是付费的，和Linux的开源精神不符。

不过，到了2002年，Linux系统已经发展了十年了，代码库之大让Linus很难继续通过手工方式管理了，社区的弟兄们也对这种方式表达了强烈不满，于是Linus选择了一个商业的版本控制系统BitKeeper，BitKeeper的东家BitMover公司出于人道主义精神，授权Linux社区免费使用这个版本控制系统。

安定团结的大好局面在2005年就被打破了，原因是Linux社区牛人聚集，不免沾染了一些梁山好汉的江湖习气。开发Samba的Andrew试图破解BitKeeper的协议（这么干的其实也不只他一个），被BitMover公司发现了（监控工作做得不错！），于是BitMover公司怒了，要收回Linux社区的免费使用权。

Linus可以向BitMover公司道个歉，保证以后严格管教弟兄们，嗯，这是不可能的。实际情况是这样的：

Linus花了两周时间自己用C写了一个分布式版本控制系统，这就是Git！一个月之内，Linux系统的源码已经由Git管理了！牛是怎么定义的呢？大家可以体会一下。

Git迅速成为最流行的分布式版本控制系统，尤其是2008年，GitHub网站上线了，它为开源项目免费提供Git存储，无数开源项目开始迁移至GitHub，包括jQuery，PHP，Ruby等等。

历史就是这么偶然，如果不是当年BitMover公司威胁Linux社区，可能现在我们就没有免费而超级好用的Git了。

## 3、分布式 VS 集中式

# # Git 安装

在使用Git前我们需要先安装 Git。Git 目前支持 Linux/Unix、Solaris、Mac和 Windows 平台上运行。

Git 各平台安装包下载地址为：<http://git-scm.com/downloads>

下载安装即可，安装好之后，输入指令，查看 git 安装位置及其版本。

```shell
$ which git
/usr/local/bin/git
$ git --version
git version 2.15.0
```

> 提示：windows 下需将 *which* 替换成 *where*.

## 1、配置用户信息

配置个人的用户名称和电子邮件地址：

```shell
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

如果用了 `--global` 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。

如果要在某个特定的项目中使用其他名字或者电邮，只要去掉 `--global` 选项重新配置即可，新的设定保存在当前项目的 *.git/config* 文件里。

## 2、查看配置信息

输入指令

```shell
$ git config --list
```

# # Git 工作流程

## 1、提交代码流程：

Fork主仓库 -> 

clone自己的远程仓库 -> 

修改本地仓库代码 ->

 add/commit/push到自己的远程仓库 -> pull request

## 2、更新代码流程

撤销缓存区的全部修改 -> 

remote add 别名 git 地址 ->

pull 别名 分支名

push 到自己的远程仓库

# # Git 创建版本库

版本库又称为仓库，英文名 “repository”，你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

所以，创建一个版本库非常简单。

首先，选择一个合适的地方，创建一个空目录，然后在终端中打开：

```shell
$ cd /Users/LiHongyao/Desktop/git_repository
$ pwd
/Users/LiHongyao/Desktop/git_repository
```

我在桌面上创建了一个 git_repository 的空目录。`pwd` 命令用于显示当前目录。

然后，通过 `git init` 命令把这个目录变成Git可以管理的仓库：

```shell
$ git init
Initialized empty Git repository in /Users/LiHongyao/Desktop/git_repository/.git/
```

初始化后，会在 git_repository 目录下会出现一个名为 `.git` 的目录，这个目录是Git来跟踪管理版本库的，所有 Git 需要的数据和资源都存放在这个目录中。

# # Git 基本操作

## 1、添加文件至版本库

再此之前，可先安装一个 **Notepad++** 编辑工具。

我们先创建一个 “README.md”（ `*.md` 为markdown文件）文件放置在 “git_repositorie” 目录下，文件内容为（内容不限）：

```shell
Git is a version control system.
Git is free software.
```

如果你是 macOS 系统，可通过如下命令创建。

```shell
$ touch README.md
$ vim README.md
```

macOS 在终端可输入以上指令创建/编辑 “README.md” 文件，在 vim 中，输入 `i` 进行编辑，编辑完成之后 按 `ESC` 退出编辑状态输入 `:wq` 保存退出即可。macOS下还可通过以下指令查看 *README.md* 文件的内容：

```shell
$ cat README.md
```

> 提示：windows 下可使用 `echo > README.md` 指令或通过文本编辑器编辑文本添加。

将文件添加至版本库只需要两个步骤，如下所示：

**第1步**：用命令 `git add` 告诉Git，把文件添加到仓库：

```shell
$ git add README.md
```

> 提示：执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

我们可通过该指令添加多个文件，如下所示：

```shell
$ git add file1.md
$ git add file2.md
$ git add file3.md
```

显然这样会比较麻烦，通过如下指令可将所有更新/删除/新建的文件添加到仓库。

```shell
$ git add -A
```

**第2步**：用命令 `git commit` 告诉Git，把文件提交到仓库：

```shell
$ git commit -m "wrote a readme file"
[master (root-commit) 0ba5814] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 README.md
```

> 提示：
>
> `-m` ：该参数用于设置提交说明，可以输入任意内容，便于我们在历史记录查找。

## 2、提交修改

- `git status`：查看工作区状态
- `git diff`：查看修改

我们已经成功添加了 “README.md” 文件，接下来修改 “README.md” 文件内容如下：

```shell
Git is a distributed version control system.
Git is free software.
```

运行 `git status` 命令查看结果：

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

`git status` 命令可以让我们时刻掌握仓库当前的状态，上面的命令告诉我们，“README.md” 被修改过了，但还没有准备提交的修改。

我们可通过 `git diff` 指令查看做了哪些修改：

```shell
$ git diff
diff --git a/README.md b/README.md
index 46d49bf..9247db6 100644
--- a/README.md
+++ b/README.md
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```

接下来，我们提交修改，提交修改与提交文件是一样的。

```shell
$ git add "README.md"
```

在执行 `git commit` 之前，我们再来查看一下状态：

```shell
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
```

`git status` 告诉我们，将要被提交的修改包括 “README.md” ，下一步就可直接提交了：

```shell
$ git commit -m "add distributed"
[master 725657e] add distributed
 1 file changed, 1 insertion(+), 1 deletion(-)
```

提交后，我们再用 `git status` 命令看看仓库的当前状态：

```shell
$ git status
On branch master
nothing to commit, working tree clean
```

Git告诉我们当前没有需要提交的修改，而且，工作树是干净（ “working tree clean” ）的。

## 3、版本回退

现在，你已经学会了修改文件，然后把修改提交到Git版本库，那么我们再练习一次，修改 “README.md” 文件如下：

```shell
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

然后尝试提交：

```shell
$ git add "README.md"
$ git commit -m "append GPL"
[master 9ed2515] append GPL
 1 file changed, 1 insertion(+), 1 deletion(-)
```

像这样，你不断对文件进行修改，然后不断提交修改到版本库里，那么版本库就会记录提交的多个版本，我们可通过 `git log` 指令查看历史版本：

```shell
$ git log
commit 9ed2515ca3f3ba0e677ccb13a17756a287e04829 (HEAD -> master)
Author: LiHongyao <lihy_online@163.com>
Date:   Tue Jan 16 19:06:35 2018 +0800

    append GPL

commit 725657efad241b7eaa5e8528797591d2cefa02b3
Author: LiHongyao <lihy_online@163.com>
Date:   Tue Jan 16 18:58:53 2018 +0800

    add distributed

commit 0ba5814bca78a464947b3734b5abb3eb868216fc
Author: LiHongyao <lihy_online@163.com>
Date:   Tue Jan 16 17:50:02 2018 +0800

    wrote a readme file
```

`git log` 命令显示从最近到最远的提交日志，我们可以看到3次提交：

最近的一次是 “append GPL”，

上一次是 “add distributed” ，

最早的一次是 “wrote a readme file”。

如果嫌输出信息太多，看得眼花缭乱的，可以试试加上 `--pretty=oneline` 参数：

```shell
$ git log --pretty=oneline
9ed2515ca3f3ba0e677ccb13a17756a287e04829 (HEAD -> master) append GPL
725657efad241b7eaa5e8528797591d2cefa02b3 add distributed
0ba5814bca78a464947b3734b5abb3eb868216fc wrote a readme file
```

> 提示：上述结果中类似 “725657….” 的字符串为 “commit id”（版本号）。
>

现在，我们假设，如果你需要回退到上一个版本，也就是 "add distributed" 这个版本，我们应该如何实现呢？

首先，Git必须知道当前版本是哪个版本，在Git中，用 `HEAD`  表示当前版本，也就是最新的提交`9ed25...04829`（ 注意：我的提交ID和你的肯定不一样 ），上一个版本就是 `HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个 `^` 比较容易数不过来，所以写成 `HEAD~100`。

我们要把当前版本 “append GPL”  回退到上一个版本 “add distributed”，就可以使用 `git reset` 命令：

```shell
$ git reset --hard HEAD^
HEAD is now at 725657e add distributed
```

> 提示：windows 系统需要通过双引号将 `^` 括起来，如：git reset --hard HEAD“^”

接下来我们查看一下 “README.md” 文件内容是否为 ”add distributed“  版本内容：

```shell
$ cat README.md
Git is a distributed version control system.
Git is free software.
```

果然，内容已经回退到了 ”add distributed“  版本内容。

接下来，我们再来查看一下版本历史记录：

```shell
$ git log --pretty=oneline
725657efad241b7eaa5e8528797591d2cefa02b3 (HEAD -> master) add distributed
0ba5814bca78a464947b3734b5abb3eb868216fc wrote a readme file
```

最新的那个版本 ”append GPL“ 已经看不到了，如果你突然反悔了，又想回到  ”append GPL“  版本怎么办呢？只要你的终端窗口没有关闭，你就可以往上找，找到  ”append GPL“  的版本号，使用如下指令即可：

```shell
$ git reset --hard 9ed2515ca3f3ba0e677ccb13a17756a287e04829
HEAD is now at 9ed2515 append GPL
```

这样，就可以指定回到 “commit id” 对应的那个版本了。

> 提示：版本号没必要写全，前几位就可以了，Git会自动去找。当然也不能只写前一两位，因为Git可能会找到多个版本号，就无法确定是哪一个了
>

我们在查看一下 "README.md" 文件的内容：

```shell
$ cat README.md
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

果然，我胡汉三又回来啦~

Git的版本回退速度非常快，因为Git在内部有个指向当前版本的 `HEAD` 指针，当你回退版本的时候，Git仅仅是把HEAD从指向 ”append GPL“ 改为指向 ”add distributed“，然后顺便把工作区的文件更新了。所以你让 `HEAD` 指向哪个版本号，你就把当前版本定位在哪。

现在，你回退到了某个版本，关掉电脑，第二天你又想恢复到新版本怎么办呢？

在Git中，总是有后悔药可以吃的。当你用 `$ git reset --hard HEAD^` 回退到 ”add distributed* 版本时，再想恢复到 ”append GPL“ ，就必须找到 ”append GPL“ 的 commit id。Git提供了一个命令 `git reflog` 用来记录你的每一次命令：

```shell
$ git reflog
9ed2515 (HEAD -> master) HEAD@{0}: reset: moving to 9ed2515ca3f3ba0e677ccb13a17756a287e04829
725657e HEAD@{1}: reset: moving to HEAD^
9ed2515 (HEAD -> master) HEAD@{2}: commit: append GPL
725657e HEAD@{3}: commit: add distributed
0ba5814 HEAD@{4}: commit (initial): wrote a readme file
```

现在我们找到了 ”append GPL“  版本的id之后，就可以进行回退啦。

> 本节知识点回顾：
>
> 1. `HEAD` 指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令:
>
>     ```shell
>        $ git reset --hard commit_id
>     ```
>
> 2. 穿梭前，用 `git log` 可以查看提交历史，以便确定要回退到哪个版本。
>
> 3. 要重返未来，用 `git reflog` 查看命令历史，以便确定要回到未来的哪个版本。

## 4、工作区和暂存区

Git和其他版本控制系统如SVN的一个不同之处就是有暂存区的概念。

> 工作区：*Working  tree*

就是你在电脑里能看到的目录，比如我的 *git_repository* 文件夹就是一个工作区：

> 版本库：*Repository*

工作区有一个隐藏目录 `.git`，这个不算工作区，而是Git的版本库。

Git 的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支 `master`，以及指向 `master`的一个指针叫`HEAD`。

![0](https://user-images.githubusercontent.com/12387544/35046593-6cf46810-fbd2-11e7-9885-4b3a6421f879.jpeg)

分支和 HEAD 的概念我们以后再讲。

前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：

第一步是用 `git add` 把文件添加进去，实际上就是把文件修改添加到暂存区；

第二步是用 `git commit` 提交更改，实际上就是把暂存区的所有内容提交到当前分支。

因为我们创建Git版本库时，Git自动为我们创建了唯一一个 ”master“ 分支，所以，现在，`git commit` 就是往 ”master“ 分支上提交更改。

你可以简单理解为，需要提交的文件修改放到暂存区，然后，一次性提交暂存区的所有修改。

我们来练习一下，修改 "README.md" 文件，增加一行语句，如下所示：

```shell
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
```

然后，在工作区新增一个 ”LICENSE“ 文本文件（内容随便写）。

先用 `git status` 查看一下状态：

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	LICENSE

no changes added to commit (use "git add" and/or "git commit -a")
```

Git非常清楚地告诉我们， “README.md” 被修改了，而 ”LICENSE“ 还从来没有被添加过，所以它的状态是 `Untracked`。

现在，使用两次命令 `git add`，把  “README.md” 和 ”LICENSE“ 都添加后，用 `git status` 再查看一下：

```shell
$ git add README.md
$ git add LICENSE
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   LICENSE
	modified:   README.md
```

现在，暂存区的状态就变成这样了：

![1](https://user-images.githubusercontent.com/12387544/35046629-836608c4-fbd2-11e7-960b-dff1311c206a.jpeg)

所以，`git add` 命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行`git commit`就可以一次性把暂存区的所有修改提交到分支。

```shell
$ git commit -m "understand how stage works"
[master 707e250] understand how stage works
 2 files changed, 3 insertions(+)
 create mode 100644 LICENSE
```

一旦提交后，如果你又没有对工作区做任何修改，那么工作区就是“干净”的：

```shell
$ git status
On branch master
nothing to commit, working tree clean
```

现在版本库变成了这样，暂存区就没有任何内容了：

![3](https://user-images.githubusercontent.com/12387544/35046717-c4cbd0aa-fbd2-11e7-9877-00b625192d1d.jpeg)



## 5、管理修改

现在，假定你已经完全掌握了暂存区的概念。下面，我们要讨论的就是，为什么Git比其他版本控制系统设计得优秀，因为Git跟踪并管理的是修改，而非文件。

你会问，什么是修改？比如你新增了一行，这就是一个修改，删除了一行，也是一个修改，更改了某些字符，也是一个修改，删了一些又加了一些，也是一个修改，甚至创建一个新文件，也算一个修改。

为什么说Git管理的是修改，而不是文件呢？我们还是做实验。第一步，对 “README.md” 做一个修改，比如加一行内容：

```
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes.
```

然后添加：

```shell
$ git add "README.md"
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
```

然后，再修改：

```
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
```

提交：

```shell
$ git commit -m "git tracks changes"
[master 3adc08e] git tracks changes
 1 file changed, 3 insertions(+), 1 deletion(-)
```

提交后，再看看状态：

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

怎么第二次的修改没有被提交？我们来回顾一下操作过程：

第一次修改 -> `git add` -> 第二次修改 -> `git commit`

你看，我们前面讲了，Git管理的是修改，当你用`git add`命令后，在工作区的第一次修改被放入暂存区，准备提交，但是，在工作区的第二次修改并没有放入暂存区，所以，`git commit`只负责把暂存区的修改提交了，也就是第一次的修改被提交了，第二次的修改不会被提交。

提交后，用 `git diff HEAD -- README.md`命令可以查看工作区和版本库里面最新版本的区别：

```shell
$ git diff HEAD -- README.md
diff --git a/README.md b/README.md
index 5a35689..b964d55 100644
--- a/README.md
+++ b/README.md
@@ -4,4 +4,4 @@ Git is free software distributed under the GPL.
 
 Git has a mutable index called stage.
 
-Git tracks changes.
\ No newline at end of file
+Git tracks changes of files.
\ No newline at end of file
```

可见，第二次修改确实没有被提交。

那怎么提交第二次修改呢？你可以继续`git add`再`git commit`，也可以别着急提交第一次修改，先`git add`第二次修改，再`git commit`，就相当于把两次修改合并后一块提交了：

第一次修改 -> `git add` -> 第二次修改 -> `git add` -> `git commit`

好，现在，把第二次修改提交了，然后开始小结。

> 小结：
>
> 现在，你又理解了Git是如何跟踪修改的，每次修改，如果不`add`到暂存区，那就不会加入到`commit`中。

## 6、撤销修改

如果你不小心在你的 ”README.md“ 文件中加了一行语句：

```
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
My stupid boss still prefers SVN.
```

在你准备提交前，你猛然发现了“stupid boss”可能会让你丢掉这个月的奖金！

既然错误发现得很及时，就可以很容易地纠正它。你可以删掉最后一行，手动把文件恢复到上一个版本的状态。如果用 `git status` 查看一下：

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

你可以发现，Git会告诉你，`git checkout -- file` 可以丢弃工作区的修改：

```shell
$ git checkout -- README.md
```

命令 `git checkout -- README.md`  意思就是，把 “README.md” 文件在工作区的修改全部撤销，这里有两种情况：

一种是  "README.md" 至修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是  "README.md" 已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

总之，就是让这个文件回到最近一次`git commit`或`git add`时的状态。

现在，看看  "README.md"  的文件内容：

```shell
$ cat "README.md"
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
```

文件内容果然复原了。

> 提示：
>
> `git checkout -- file`命令中的`--`很重要，没有`--`，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到`git checkout`命令。

还有一种情况，就是你不小心添加了一条语句，还 `git add` 到暂存区了：

```shell
$ cat "README.md"
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
My stupid boss still prefers SVN.
$ git add "README.md"
```

庆幸的是，在`commit`之前，你发现了这个问题。用`git status`查看一下，修改只是添加到了暂存区，还没有提交：

```shell
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
```

Git同样告诉我们，用命令`git reset HEAD file`可以把暂存区的修改撤销掉（unstage），重新放回工作区：

```shell
$ git reset HEAD "README.md"
Unstaged changes after reset:
M	README.md
```

`git reset` 命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用`HEAD`时，表示最新的版本。

再用`git status`查看一下，现在暂存区是干净的，工作区有修改：

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

还记得如何丢弃工作区的修改吗？

```shell
$ git checkout -- README.md
$ git status
On branch master
nothing to commit, working tree clean
```

整个世界终于清静了！

现在，假设你不但改错了东西，还从暂存区提交到了版本库，怎么办呢？还记得[版本回退]()一节吗？可以回退到上一个版本。不过，这是有条件的，就是你还没有把自己的本地版本库推送到远程。还记得Git是分布式版本控制系统吗？我们后面会讲到远程版本库，一旦你把“stupid boss”提交推送到远程版本库，你就真的惨了……

> 小结：
>
> 1. 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- file`。
> 2. 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD file`，就回到了1，第二步按1操作。
> 3. 已经提交了不合适的修改到版本库时，想要撤销本次提交，参考[版本回退]()一节，不过前提是没有推送到远程库。

## 7、删除文件

在Git中，删除也是一个修改操作，我们实战一下，先添加一个新文件test.md到Git并且提交：

```shell
$ touch test.md
$ git add "test.md"
$ git commit -m "add test.md"
[master b6e477c] add test.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test.md
```

一般情况下，你通常直接在文件管理器中把没用的文件删了，或者用`rm`命令删了：

```shell
$ rm test.md
```

这个时候，Git知道你删除了文件，因此，工作区和版本库就不一致了，`git status`命令会立刻告诉你哪些文件被删除了：

```shell
git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    test.md
```

现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`：

```shell
git rm test.md
rm 'test.md'
$ git commit -m "remove test.md"
[master 7b08dab] remove test.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 test.md
```

现在，文件就从版本库中被删除了。

另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：

```shell
$ git checkout -- test.md
```

`git checkout `其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

> 小结：
>
> 命令`git rm`用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失**最近一次提交后你修改的内容**。

# # 远程仓库

到目前为止，我们已经掌握了如何在Git仓库里对一个文件进行操作，你再也不用担心文件备份或者丢失的问题了。

可是有用过集中式版本控制系统SVN的童鞋会站出来说，这些功能在SVN里早就有了，没看出Git有什么特别的地方。

没错，如果只是在一个仓库里管理文件历史，Git和SVN真没啥区别。为了保证你现在所学的Git物超所值，将来绝对不会后悔，同时为了打击已经不幸学了SVN的童鞋，本章开始介绍Git的杀手级功能之一（注意是之一，也就是后面还有之二，之三……）：**远程仓库**。

Git是分布式版本控制系统，同一个Git仓库，可以分布到不同的机器上。怎么分布呢？最早，肯定只有一台机器有一个原始版本库，此后，别的机器可以“克隆”这个原始版本库，而且每台机器的版本库其实都是一样的，并没有主次之分。

你肯定会想，至少需要两台机器才能玩远程库不是？但是我只有一台电脑，怎么玩？

其实一台电脑上也是可以克隆多个版本库的，只要不在同一个目录下。不过，现实生活中是不会有人这么傻的在一台电脑上搞几个远程库玩，因为一台电脑上搞几个远程库完全没有意义，而且硬盘挂了会导致所有库都挂掉，所以我也不告诉你在一台电脑上怎么克隆多个仓库。

实际情况往往是这样，找一台电脑充当服务器的角色，每天24小时开机，其他每个人都从这个“服务器”仓库克隆一份到自己的电脑上，并且各自把各自的提交推送到服务器仓库里，也从服务器仓库中拉取别人的提交。

完全可以自己搭建一台运行Git的服务器，不过现阶段，为了学Git先搭个服务器绝对是小题大作。好在这个世界上有个叫[GitHub](https://github.com/)的神奇的网站，从名字就可以看出，这个网站就是提供Git仓库托管服务的，所以，只要注册一个GitHub账号，就可以免费获得Git远程仓库。

在继续阅读后续内容前，请自行注册GitHub账号。由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以，需要一点设置：

**第1步：**创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有 ”id_rsa“ 和 ”id_rsa.pub“ 这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：

```shell
$ ssh-keygen -t rsa -C "youremail@example.com"
```

你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。

如果一切顺利的话，可以在用户主目录里找到 ”.ssh“ 目录，里面有 ”id_rsa“ 和 ”id_rsa.pub” 两个文件，这两个就是SSH Key的秘钥对， ”id_rsa“  是私钥，不能泄露出去， ”id_rsa.pub” 是公钥，可以放心地告诉任何人。

**第2步：**

登陆Github -> 点击右上角个人头像 -> 点击Settings进入设置页面 ->

点击SSH and GPG keys选项 -> 点击右上角New SSH key ->  

在添加面板中，

Title：设置SSH key 标题，可任意填写

Key：将  *”id_rsa.pub”*  文件内容拷贝至此

然后点击 Add SSH Key 就可以看到你创建的SSH Key了，如下图所示：

![3](https://user-images.githubusercontent.com/12387544/35029605-b0bf9088-fb96-11e7-9ac1-310e9cb2be34.png)



为什么GitHub需要SSH Key呢？因为GitHub需要识别出你推送的提交确实是你推送的，而不是别人冒充的，而Git支持SSH协议，所以，GitHub只要知道了你的公钥，就可以确认只有你自己才能推送。

当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。

最后友情提示，在GitHub上免费托管的Git仓库，任何人都可以看到喔（但只有你自己才能改）。所以，不要把敏感信息放进去。

如果你不想让别人看到Git库，有两个办法，一个是交点保护费，让GitHub把公开的仓库变成私有的，这样别人就看不见了（不可读更不可写）。另一个办法是自己动手，搭一个Git服务器，因为是你自己的Git服务器，所以别人也是看不见的。这个方法我们后面会讲到的，相当简单，公司内部开发必备。

确保你拥有一个GitHub账号后，我们就即将开始远程仓库的学习。

> 小结：
>
> “有了远程仓库，妈妈再也不用担心我的硬盘了。”——Git点读机

## 1、添加远程库

现在的情景是，你已经在本地创建了一个Git仓库后，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步，这样，GitHub上的仓库既可以作为备份，又可以让其他人通过该仓库来协作，真是一举多得。

首先，登陆GitHub，然后，在右上角找到点击 `+` 按钮，再选择 “New Repository” 创建一个新的仓库：



在 “Repository name“ 填入 “GITTesting”，其他保持默认设置，点击 “Create repository” 按钮，就成功地创建了一个新的Git仓库：



目前，在GitHub上的这个 “GITTesting” 仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

现在，我们根据GitHub的提示，在本地的 “GITTesting”  仓库下运行命令：

```shell
$ git remote add origin https://github.com/jifengjxx/GITTesting.git
```

请千万注意，把上面的 `LiHongyao` 替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。

添加后，远程库的名字就是 `origin`，这是Git默认的叫法，也可以改成别的，但是`origin`这个名字一看就知道是远程库。

下一步，就可以把本地库的所有内容推送到远程库上：

```shell
$ git push -u origin master
Counting objects: 22, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (18/18), done.
Writing objects: 100% (22/22), 1.83 KiB | 939.00 KiB/s, done.
Total 22 (delta 6), reused 0 (delta 0)
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/LiHongyao/GITTesting.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

把本地库的内容推送到远程，用 `git push`命令，实际上是把当前分支 `master` 推送到远程。

由于远程库是空的，我们第一次推送 `master` 分支时，加上了 `-u` 参数，Git不但会把本地的`master` 分支内容推送的远程新的 `master` 分支，还会把本地的 `master` 分支和远程的 `master` 分支关联起来，在以后的推送或者拉取时就可以简化命令。

推送成功后，可以立刻在GitHub页面中看到远程库的内容已经和本地一模一样：



从现在起，只要本地作了提交，就可以通过命令：

```shell
$ git push origin master
```

把本地`master`分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！



**SSH 警告**

当你第一次使用Git的`clone`或者`push`命令连接GitHub时，会得到一个警告：

```shell
The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?
```

这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入`yes`回车即可。

Git会输出一个警告，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：

```
Warning: Permanently added 'github.com' (RSA) to the list of known hosts.
```

这个警告只会出现一次，后面的操作就不会有任何警告了。

如果你实在担心有人冒充GitHub服务器，输入`yes`前可以对照[GitHub的RSA Key的指纹信息](https://help.github.com/articles/what-are-github-s-ssh-key-fingerprints/)是否与SSH连接给出的一致。

> 小结：
>
> 要关联一个远程库，使用命令：
>
> `git remote add origin git@server-name:path/repo-name.git`；
>
> 关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；
>
> 此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；
>
> 分布式版本系统的最大好处之一是在本地工作完全不需要考虑远程库的存在，也就是有没有联网都可以正常工作，而SVN在没有联网的时候是拒绝干活的！当有网络的时候，再把本地提交推送一下就完成了同步，真是太方便了！

## 2、克隆远程库

上一小节中，我们讲了先有本地库，后有远程库的时候，如何关联远程库。

现在，假设我们从零开发，那么最好的方式是先创建远程库，然后，从远程库克隆。

首先，登陆GitHub，创建一个新的仓库，名字叫：`GITProj`：



注意：创建新的仓库时，勾选 “Initialize this repository with a README” , 这样GitHub会自动为我们创建一个`README.md`文件。创建完毕后，可以看到`README.md`文件：



现在，远程库已经准备好了，下一步是用命令`git clone`克隆一个本地库：

```shell
$ git clone git@github.com:jifengjxx/GITProj.git
Cloning into 'GITProj'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
```

注意把Git库的地址换成你自己的，然后进入 “GITProj” 目录看看，已经有 `README.md` 文件了。

如果有多个人协作开发，那么每个人各自从远程克隆一份就可以了。

你也许还注意到，GitHub给出的地址不止一个，可以用 

- *git@github.com:jifengjxx/GITProj.git*

这样的地址。实际上，Git支持多种协议，默认的 `git://`使用ssh，但也可以使用`https`等其他协议。使用`https`除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用`ssh`协议而只能用`https`。

> 小结：
>
> 1. 要克隆一个仓库，首先必须知道仓库的地址，然后使用`git clone`命令克隆。
> 2. Git支持多种协议，包括`https`，但通过`ssh`支持的原生`git`协议速度最快。

# # 分支管理

分支就是科幻电影里面的平行宇宙，当你正在电脑前努力学习Git的时候，另一个你正在另一个平行宇宙里努力学习SVN。

如果两个平行宇宙互不干扰，那对现在的你也没啥影响。不过，在某个时间点，两个平行宇宙合并了，结果，你既学会了Git又学会了SVN！

![9](https://user-images.githubusercontent.com/12387544/35029509-2f4dbdea-fb96-11e7-97f5-ae1f85266d32.png)

分支在实际中有什么用呢？假设你准备开发一个新功能，但是需要两周才能完成，第一周你写了50%的代码，如果立刻提交，由于代码还没写完，不完整的代码库会导致别人不能干活了。如果等代码全部写完再一次提交，又存在丢失每天进度的巨大风险。

现在有了分支，就不用怕了。你创建了一个属于你自己的分支，别人看不到，还继续在原来的分支上正常工作，而你在自己的分支上干活，想提交就提交，直到开发完毕后，再一次性合并到原来的分支上，这样，既安全，又不影响别人工作。

其他版本控制系统如SVN等都有分支管理，但是用过之后你会发现，这些版本控制系统创建和切换分支比蜗牛还慢，简直让人无法忍受，结果分支功能成了摆设，大家都不去用。

但Git的分支是与众不同的，无论创建、切换和删除分支，Git在1秒钟之内就能完成！无论你的版本库是1个文件还是1万个文件。

## 1、创建与合并分支                                                        

在 [版本回退]() 里，你已经知道，每次提交，Git都把它们串成一条时间线，这条时间线就是一个分支。截止到目前，只有一条时间线，在Git里，这个分支叫主分支，即 `master` 分支。`HEAD` 严格来说不是指向提交，而是指向 `master`，`master` 才是指向提交的，所以，`HEAD` 指向的就是当前分支。

一开始的时候，`master` 分支是一条线，Git用 `master`指向最新的提交，再用`HEAD`指向`master`，就能确定当前分支，以及当前分支的提交点：

![10](https://user-images.githubusercontent.com/12387544/35029490-18c5bb4a-fb96-11e7-8238-8f4f052df91d.png)

每次提交，`master` 分支都会向前移动一步，这样，随着你不断提交，`master`分支的线也越来越长。

当我们创建新的分支，例如 `dev` 时，Git 新建了一个指针叫 `dev`，指向 `master` 相同的提交，再把 `HEAD` 指向 `dev`，就表示当前分支在 `dev` 上：

![11](https://user-images.githubusercontent.com/12387544/35029472-04b8171a-fb96-11e7-9545-32640704af87.png)

你看，Git 创建一个分支很快，因为除了增加一个 `dev`指针，改改`HEAD`的指向，工作区的文件都没有任何变化！

不过，从现在开始，对工作区的修改和提交就是针对 `dev` 分支了，比如新提交一次后，`dev` 指针往前移动一步，而 `master` 指针不变：

![12](https://user-images.githubusercontent.com/12387544/35029375-a83c1f7c-fb95-11e7-916d-858d0b248c7c.png)

假如我们在 `dev` 上的工作完成了，就可以把 `dev` 合并到 `master` 上。Git怎么合并呢？最简单的方法，就是直接把 `master` 指向 `dev` 的当前提交，就完成了合并.

![13](https://user-images.githubusercontent.com/12387544/35029358-93a32074-fb95-11e7-878e-286f84ee5c82.png)

所以Git合并分支也很快！就改改指针，工作区内容也不变！

合并完分支后，甚至可以删除`dev`分支。删除`dev`分支就是把`dev`指针给删掉，删掉后，我们就剩下了一条`master`分支：

![14](https://user-images.githubusercontent.com/12387544/35029189-b79adefa-fb94-11e7-94f1-1e8958b269fa.png)

下面开始实战：

首先，我们创建 `dev` 分支，然后切换到 `dev` 分支：

```shell
$ git checkout -b dev
Switched to a new branch 'dev'
```

`git checkout `命令加上 `-b` 参数表示创建并切换，相当于以下两条命令：

```shell
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
```

然后，用 `git branch` 命令查看当前分支：

```shell
$ git branch
* dev
  master
```

`git branch` 命令会列出所有分支，当前分支前面会标一个`*`号。

然后，我们就可以在 `dev` 分支上正常提交，比如对 “README.md” 文件做个修改，加上一行：

```
Creating a new branch is quick.
```

然后提交：

```shell
$ git add README.md
$ git commit -m "branch test"
[dev e433476] branch test
 1 file changed, 2 insertions(+), 1 deletion(-)
```

现在，`dev` 分支的工作完成，我们就可以切换回 `master` 分支：

```shell
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
$ git branch
  dev
* master
```

切换回 `master` 分支后，再查看一个  “README.md” 文件，刚才添加的内容不见了！因为那个提交是在 `dev` 分支上，而 `master` 分支此刻的提交点并没有变：

![15](https://user-images.githubusercontent.com/12387544/35030038-a2a3be14-fb98-11e7-83a9-c6de989c5a8a.png)

现在，我们把 `dev` 分支的工作成果合并到 `master` 分支上：

```shell
$ git merge dev
Updating dcfb8f2..e433476
Fast-forward
 README.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

`git merge `命令用于合并指定分支到当前分支。合并后，再查看 “README.md”  的内容，就可以看到，和`dev`分支的最新提交是完全一样的。

> 注意：
>
> 上面的  *“Fast-forward”*  信息，Git告诉我们，这次合并是“快进模式”，也就是直接把`master`指向`dev`的当前提交，所以合并速度非常快

当然，也不是每次合并都能 “Fast-forward” ，我们后面会讲其他方式的合并。

合并完成后，就可以放心地删除 `dev` 分支了：

```shell
$ git branch -d dev
Deleted branch dev (was e433476).
```

删除后，查看 `branch`，就只剩下`master`分支了：

```shell
$ git branch
* master
```

因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在`master`分支上工作效果是一样的，但过程更安全。

> 小结：

1. Git鼓励大量使用分支：
2. 查看分支：`git branch`
3. 创建分支：`git branch <name>`
4. 切换分支：`git checkout <name>`
5. 创建+切换分支：`git checkout -b <name>`
6. 合并某分支到当前分支：`git merge <name>`
7. 删除分支：`git branch -d <name>`

## 2、解决冲突

合并分支往往也不是一帆风顺的，可能会出现冲突。

准备新的 `feature` 分支，继续我们的新分支开发：

```shell
$ git checkout -b feature
Switched to a new branch 'feature'
```

修改 “README.md” 文件最后一行为：

```
Creating a new branch is quick AND simple.
```

在 `feature` 分支上提交：

```shell
$ git add "README.md"
$ git commit -m "And simple"
[feature 3bf80e1] And simple
 1 file changed, 1 insertion(+), 1 deletion(-)
```

切换到 `master` 分支：

```shell
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

在 `master` 分支上把 “README.md”  文件的最后一行改为：

```
Creating a new branch is quick & simple.
```

提交：

```shell
$ git add "README.md"
$ git commit -m "& simple"
[master 103a7f9] & simple
 1 file changed, 1 insertion(+), 1 deletion(-)
```

现在，`master` 分支和 `feature` 分支各自都分别有新的提交，变成了这样：

![16](https://user-images.githubusercontent.com/12387544/35031675-ea605374-fb9e-11e7-99c6-b79ed67c7165.png)

这种情况下，Git无法执行“快速合并”，只能试图把各自的修改合并起来，但这种合并就可能会有冲突，我们试试看：

```shell
$ git merge feature
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

果然冲突了！Git告诉我们，“README.md” 文件存在冲突，必须手动解决冲突后再提交。`git status` 也可以告诉我们冲突的文件：

```shell
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

	both modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

我们可以直接查看 “README.md”  的内容：

```shell
$ cat README.md
# GITProj
<<<<<<< HEAD
Creating a new branch & quick.
=======
Creating a new branch is quick AND simple.
>>>>>>> feature
```

Git用 `<<<<<<<`，`=======`，`>>>>>>>` 标记出不同分支的内容，我们修改如下后保存：

```
Creating a new branch is quick and simple.
```

再提交

```shell
$ git add README.md
$ git commit -m "conflict fixed"
[master 8e7e3d8] conflict fixed
```

现在，`master` 分支和 `feature`分支变成了下图所示：

![17](https://user-images.githubusercontent.com/12387544/35031759-4bef2796-fb9f-11e7-877e-3eb54a7cebca.png)

用带参数的 `git log` 也可以看到分支的合并情况：

```shell
$ git log --graph --pretty=oneline --abbrev-commit
*   8e7e3d8 (HEAD -> master) conflict fixed
|\  
| * 3bf80e1 (feature) And simple
* | 103a7f9 & simple
|/  
* e433476 (origin/master, origin/HEAD) branch test
* dcfb8f2 Initial commit
```

最后，删除 `feature`  分支：

```shell
$ git branch -d feature
Deleted branch feature (was 3bf80e1).
```

工作完成。

> 小结：
>
> 1. 当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
> 2. 用 `git log --graph` 命令可以看到分支合并图。

## 3、分支管理策略

通常，合并分支时，如果可能，Git会用 `Fast forward` 模式，但这种模式下，删除分支后，会丢掉分支信息。

如果要强制禁用 `Fast forward` 模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

下面我们实战一下 `--no-ff` 方式的 `git merge` ：

首先，仍然创建并切换 `dev` 分支：

```shell
$ git checkout -b dev
Switched to a new branch 'dev'
```

修改 “README.md” 文件，并提交一个新的 commit：

```shell
$ git add README.md
$ git commit -m "add hello"
[dev a5191b6] add hello
 1 file changed, 2 insertions(+), 1 deletion(-)
```

现在，我们切换回 `master`：

```shell
git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)
```

准备合并 `dev` 分支，请注意 `--no-ff` 参数，表示禁用 `Fast forward`：

```shell
$ git merge --no-ff -m "merge with no-ff" dev
Merge made by the 'recursive' strategy.
 README.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

合并后，我们用 `git log` 看看分支历史：

```shell
$ git log --graph --pretty=oneline --abbrev-commit
*   c2b5888 (HEAD -> master) merge with no-ff
|\  
| * a5191b6 (dev) add hello
|/  
*   8e7e3d8 conflict fixed
...
```

可以看到，不使用 `Fast forward` 模式，merge后就像这样：

![18](https://user-images.githubusercontent.com/12387544/35033427-93cd998e-fba5-11e7-9462-a36a9551c5eb.png)

**分支策略**

在实际开发中，我们应该按照几个基本原则进行分支管理：

首先，`master` 分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；

那在哪干活呢？干活都在 `dev` 分支上，也就是说，`dev` 分支是不稳定的，到某个时候，比如1.0版本发布时，再把 `dev` 分支合并到 `master` 上，在 `master` 分支发布1.0版本；

你和你的小伙伴们每个人都在 `dev` 分支上干活，每个人都有自己的分支，时不时地往 `dev` 分支上合并就可以了。

所以，团队合作的分支看起来就像这样：

![19](https://user-images.githubusercontent.com/12387544/35033548-13f2c9c2-fba6-11e7-9d61-9fffd6296fb4.png)



> 小结：
>
> 1. Git分支十分强大，在团队开发中应该充分应用。
> 2. 合并分支时，加上 `--no-ff` 参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而 `fast forward` 合并就看不出来曾经做过合并。

## 4、Bug 分支

软件开发中，bug就像家常便饭一样。有了bug就需要修复，在Git中，由于分支是如此的强大，所以，每个bug都可以通过一个新的临时分支来修复，修复后，合并分支，然后将临时分支删除。

当你接到修复一个代号为101的bug的任务时，很自然地，你想创建一个分支 `issue-101` 来修复它，但是，等等，当前正在 `dev` 上进行的工作还没有提交，比如你正在编写一个 “Test.txt” 文件：

```shell
$ git status
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	Test.txt

nothing added to commit but untracked files present (use "git add" to track)
```

但是你这个文件现在还不能提交，怎么办呢？幸好，Git还提供了一个 `stash` 功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作：

```shell
$ git stash
Saved working directory and index state WIP on dev: b4537f9 add Test.txt
```

现在，用 `git status` 查看工作区，就是干净的（除非有没有被Git管理的文件），因此可以放心地创建分支来修复bug。

首先确定要在哪个分支上修复bug，假定需要在 `master` 分支上修复，就从 `master` 创建临时分支：

```shell
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
$ git checkout -b issue-101
Switched to a new branch 'issue-101'
```

现在修复bug，比如需要将 "README.md" 文件全部替换成如下信息来解决bug：

```
Hello, git!
```
提交：
```shell
$ git add "README.md"
$ git commit -m "fix bug 101"
[issue-101 341417c] fix bug 101
 1 file changed, 2 deletions(-)
```

修复完成后，切换到 `master` 分支，并完成合并，最后删除 `issue-101` 分支：

```shell
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

$ git merge --no-ff -m "merged bug fix 101" issue-101
Merge made by the 'recursive' strategy.
 README.md | 2 --
 1 file changed, 2 deletions(-)

$ git branch -d issue-101
Deleted branch issue-101 (was 341417c).

$ git branch
  dev
* master
```

太棒了，bug已经修复。现在，是时候接着回到`dev`分支干活了！

```shell
$ git checkout dev
Switched to branch 'dev'
$ git status
On branch dev
nothing to commit, working tree clean
```

工作区是干净的，刚才的工作现场存到哪去了？用 `git stash list` 命令看看：

```shell
$ git stash list
stash@{0}: WIP on dev: b4537f9 add Test.txt
```

工作现场还在，Git把stash内容存在某个地方了，但是需要恢复一下，有两个办法：

1. 用 `git stash apply` 恢复，但是恢复后，stash 内容并不删除，你需要用 `git stash drop` 来删除；
2. 用 `git stash pop`，恢复的同时把stash内容也删了：

```shell
$ git stash pop
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   Test.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (3425377dad942439e91506f60b72a3ab20d27e78)
```

再用 `git stash list` 查看，就看不到任何stash内容了：

```shell
$ git stash list
```

你可以多次stash，恢复的时候，先用 `git stash list` 查看，然后恢复指定的stash，用命令：

```shell
$ git stash apply stash@{0}
```

> 小结：
>
> 1. 修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；
> 2. 当手头工作没有完成时，先把工作现场 `git stash` 一下，然后去修复bug，修复后，再 `git stash pop` ，回到工作现场。



## 5、Feature 分支

软件开发中，总有无穷无尽的新的功能要不断添加进来。

添加一个新功能时，你肯定不希望因为一些实验性质的代码，把主分支搞乱了，所以，每添加一个新功能，最好新建一个feature分支，在上面开发，完成后，合并，最后，删除该feature分支。

现在，你终于接到了一个新任务：开发代号为 “god” 的新功能。

于是准备开发：

```shell
$ git checkout -b feature-god
Switched to a new branch 'feature-god'
```

5分钟后，开发完毕（添加一个 “god.md” 文件，内容随意添加）：

```shell
$ git add god.md
$ git status
On branch feature-god
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   god.md

$ git commit -m "add feature god"
[feature-god b14b0f1] add feature god
 1 file changed, 2 insertions(+)
 create mode 100644 god.md
```

切回 `master`，准备合并：

```shell
$ git checkout master
```

一切顺利的话，feature分支和bug分支是类似的，合并，然后删除。

但是，就在此时，接到上级命令，因经费不足，新功能必须取消！

虽然白干了，但是这个分支还是必须就地销毁：

```shell
$ git branch -d feature-god
error: The branch 'feature-god' is not fully merged.
If you are sure you want to delete it, run 'git branch -D feature-god'.
```

销毁失败。Git友情提醒，`feature-god` 分支还没有被合并，如果删除，将丢失掉修改，如果要强行删除，需要使用命令 `git branch -D feature-god`。

现在我们强行删除：

```shell
git branch -D feature-god
Deleted branch feature-god (was b14b0f1).
```

终于删除成功！

> 小结：
>
> 1. 开发一个新feature，最好新建一个分支；
> 2. 如果要丢弃一个没有被合并过的分支，可以通过`git branch -D <name>`强行删除。

## 6、多人协作

当你从远程仓库克隆时，实际上Git自动把本地的`master`分支和远程的`master`分支对应起来了，并且，远程仓库的默认名称是`origin`。

要查看远程库的信息，用 `git remote`：

```shell
$ git remote
origin
```

或者，用 `git remote -v` 显示更详细的信息：

```shell
$ git remote -v
origin	git@github.com:LiHongyao/GITProj.git (fetch)
origin	git@github.com:LiHongyao/GITProj.git (push)
```

上面显示了可以抓取和推送的 `origin` 的地址。如果没有推送权限，就看不到push的地址。

### 6.1、推送分支

推送分支，就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上：

```shell
$ git push origin master
```

如果要推送其他分支，比如 `dev`，就改成：

```shell
$ git push origin dev
```

但是，并不是一定要把本地分支往远程推送，那么，哪些分支需要推送，哪些不需要呢？

- `master` 分支是主分支，因此要时刻与远程同步；
- `dev` 分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
- bug 分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
- feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

总之，就是在Git中，分支完全可以在本地自己藏着玩，是否推送，视你的心情而定！

### 6.2、抓取分支

多人协作时，大家都会往 `master` 和 `dev` 分支上推送各自的修改。

现在，模拟一个你的小伙伴，可以在另一台电脑（注意要把SSH Key添加到GitHub）或者同一台电脑的另一个目录下克隆：

```shell
$ git clone git@github.com:jifengjxx/GITProj.git
Cloning into 'GITProj'...
remote: Counting objects: 31, done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 31 (delta 6), reused 27 (delta 5), pack-reused 0
Receiving objects: 100% (31/31), done.
Resolving deltas: 100% (6/6), done.
```

当你的小伙伴从远程库clone时，默认情况下，你的小伙伴只能看到本地的 `master` 分支。不信可以用 `git branch` 命令看看：

```shell
$ git branch
* master
```

现在，你的小伙伴要在 `dev` 分支上开发，就必须创建远程 `origin`的 `dev` 分支到本地，于是他用这个命令创建本地 `dev` 分支：

```shell
$ git checkout -b dev origin/dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
```

现在，他就可以在 `dev`上继续修改，然后，时不时地把`dev`分支`push`到远程：

```shell
$ git add  "README.md"
$ git commit -m "change README.md file"
[dev 4e078ab] change readme.md file
 1 file changed, 2 insertions(+)
 
$ git push origin dev
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 371 bytes | 371.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:LiHongyao/GITProj.git
   294f183..4e078ab  dev -> dev
```

你的小伙伴已经向 `origin/dev` 分支推送了他的提交，而碰巧你也对同样的文件作了修改，并试图推送：

```shell
$ git add "README.md"
$ git commit -m "change readme.md with main."
[dev 5ee4d4a] change readme.md with main.
 1 file changed, 1 insertion(+)
$ git push origin dev
To github.com:LiHongyao/GITProj.git
 ! [rejected]        dev -> dev (fetch first)
error: failed to push some refs to 'git@github.com：jifengjxx/GITProj.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

推送失败，因为你的小伙伴的最新提交和你试图推送的提交有冲突，解决办法也很简单，Git 已经提示我们，先用 `git pull` 把最新的提交从 `origin/dev` 抓下来，然后，在本地合并，解决冲突，再推送：

```shell
$ git pull
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From github.com:LiHongyao/GITProj
   294f183..4e078ab  dev        -> origin/dev
   3fa5948..294f183  master     -> origin/master
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> dev
```

`git pull` 也失败了，原因是没有指定本地 `dev` 分支与远程 `origin/dev` 分支的链接，根据提示，设置 `dev`和 `origin/dev`的链接：

```shell
$ git branch --set-upstream-to=origin/dev dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
```

再pull

```shell
$ git pull
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

这回 `git pull` 成功，但是合并有冲突，需要手动解决，解决的方法和分支管理中的 [解决冲突]()完全一样。解决后，提交，再push：

```shell
$ git add "README.md"
$ git commit -m "merge & fix README.md"
[dev e7f096d] merge & fix README.md

$ git push origin dev
Counting objects: 4, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 515 bytes | 515.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
To github.com:LiHongyao/GITProj.git
   4e078ab..e7f096d  dev -> dev
```

因此，多人协作的工作模式通常是这样：

1. 首先，可以试图用 `git push origin branch-name` 推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更新，需要先用 `git pull` 试图合并；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用 `git push origin branch-name` 推送就能成功！

如果 `git pull` 提示 *“no tracking information”*，则说明本地分支和远程分支的链接关系没有创建，用命令:

```shell
$ git branch --set-upstream branch-name origin/branch-name
```

这就是多人协作的工作模式，一旦熟悉了，就非常简单。

> 小结
>
> 1. 查看远程库信息，使用 `git remote -v`；
>
> 2. 本地新建的分支如果不推送到远程，对其他人就是不可见的；
>
> 3. 从本地推送分支，使用 `git push origin branch-name`，如果推送失败，先用 `git pull` 抓取远程的新提交；
>
> 4. 在本地创建和远程分支对应的分支，使用 
>
>    ````shell
>    $ git checkout -b branch-name origin/branch-name
>    ````
>
>    本地和远程分支的名称最好一致；
>
> 5. 建立本地分支和远程分支的关联，使用：
>
>     ```shell
>     $ git branch --set-upstream branch-name origin/branch-name
>     ```

# # 标签管理

发布一个版本时，我们通常先在版本库中打一个标签（tag），这样，就唯一确定了打标签时刻的版本。将来无论什么时候，取某个标签的版本，就是把那个打标签的时刻的历史版本取出来。所以，标签也是版本库的一个快照。

Git的标签虽然是版本库的快照，但其实它就是指向某个 commit 的指针（跟分支很像对不对？但是分支可以移动，标签不能移动），所以，创建和删除标签都是瞬间完成的。

Git有commit，为什么还要引入tag？

“请把上周一的那个版本打包发布，commit号是6a5819e...”

“一串乱七八糟的数字不好找！”

如果换一个办法：

“请把上周一的那个版本打包发布，版本号是v1.2”

“好的，按照tag v1.2查找commit就行！”

所以，tag就是一个让人容易记住的有意义的名字，它跟某个 commit 绑在一起。

## 1、创建标签

在Git中打标签非常简单，首先，切换到需要打标签的分支上：

```shell
$ git branch
* dev
  master
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

然后，敲命令 `git tag <name>` 就可以打一个新标签：

```shell
git tag v1.0
```

可以用命令 `git tag` 查看所有标签：

```shell
$ git tag
v1.0
```

默认标签是打在最新提交的 commit 上的。有时候，如果忘了打标签，比如，现在已经是周五了，但应该在周一打的标签没有打，怎么办？

方法是找到历史提交的 “commit id”，然后打上就可以了：

```shell
$ git log --pretty=oneline --abbrev-commit
294f183 (HEAD -> master, tag: v1.0, origin/master, origin/HEAD) add info.md file
b57f9b7 add gg.md
3fa5948 change
775e8c8 change Test.txt
0b325f6 merged bug fix 101
341417c fix bug 101
b4537f9 add Test.txt
c2b5888 merge with no-ff
a5191b6 add hello
8e7e3d8 conflict fixed
103a7f9 & simple
3bf80e1 And simple
e433476 branch test
```

比方说，要为 “conflict fixed”  这次提交打标签，它对应的 “commit id” 是 “8e7e3d8” ，敲入命令：

```shell
$ git tag v0.8 8e7e3d8
$ git tag
v0.8
v1.0
```

> 注意：
>
> 标签不是按时间顺序列出，而是按字母排序的。

可以用 `git show <tagname>` 查看标签信息：

```shell
$ git show v0.8
commit 8e7e3d84ff9a84188d6ef7c5167260f1ee4d8648 (tag: v0.8)
Merge: 103a7f9 3bf80e1
Author: LiHongyao <lihy_online@163.com>
Date:   Wed Jan 17 15:49:42 2018 +0800

    conflict fixed

diff --cc README.md
index e4b9dd8,fb7801c..bd85a0e
--- a/README.md
+++ b/README.md
@@@ -1,2 -1,2 +1,2 @@@
  # GITProj
- Creating a new branch & quick.
 -Creating a new branch is quick AND simple.
++Creating a new branch is quick and simple.
```

可以看到，`v0.8` 确实打在  “conflict fixed”   这次提交上。

还可以创建带有说明的标签，用 `-a` 指定标签名，`-m` 指定说明文字：

```shell
$ git tag -a <tagName> -m <des> <commit id>
```

> 小结：
>
> 1. 创建标签 ：`git tag <tagName>`
> 2. 查看标签：`git tag`
> 3. 查看标签信息：`git show <tagName>`

## 2、操作标签

如果标签打错了，也可以删除：

```shell
$ git tag -d v1.0
Deleted tag 'v1.0' (was 294f183)
```

因为创建的标签都只存储在本地，不会自动推送到远程。所以，打错的标签可以在本地安全删除。

如果要推送某个标签到远程，使用命令 `git push origin <tagname>`：

```shell
$ git push origin v0.8
Total 0 (delta 0), reused 0 (delta 0)
To github.com:LiHongyao/GITProj.git
 * [new tag]         v0.8 -> v0.8
```

或者，一次性推送全部尚未推送到远程的本地标签：

```shell
$ git push origin --tags
Total 0 (delta 0), reused 0 (delta 0)
To github.com:LiHongyao/GITProj.git
 * [new tag]         v0.1 -> v0.1
 * [new tag]         v0.5 -> v0.5
```

如果标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除：

```shell
$ git tag -d v0.5
Deleted tag 'v0.5' (was 3bf80e1)
```

然后，从远程删除。删除命令也是push，但是格式如下：

```shell
$ git push origin :refs/tags/v0.5
To github.com:LiHongyao/GITProj.git
 - [deleted]         v0.5
```

要看看是否真的从远程库删除了标签，可以登陆GitHub查看。

> 小结：
>
> - 命令：`git push origin <tagname>`可以推送一个本地标签；
> - 命令：`git push origin --tags`可以推送全部未推送过的本地标签；
> - 命令：`git tag -d <tagname>`可以删除一个本地标签；
> - 命令：`git push origin :refs/tags/<tagname>`可以删除一个远程标签。

# # 同步更新FORK仓库

如果fork源仓库更新了内容，要更新fork之后的内容，操作如下：

1. 查看远程信息

```shell
$ git remote -v
```

2. 添加远程库

```shell
$ git remote add upstream https://github.com/xxx/xxx(fork源仓库地址)
```

3. 从fork源仓库同步更新代码

```shell
$ git fetch upstream
```

4. 合并到本地代码

```shell
$ git merge upstream/master
```

5. 更新并合并自己远程仓库的代码

```shell
$ git pull origin master
```

6. 向自己远程仓库推送刚才同步源仓库后的代码

```shell
$ git push origin master
```
















