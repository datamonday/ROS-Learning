<!-- TOC -->

  - [一、基础功能](#一基础功能) 
      - [1.创建提交](#1创建提交)
      - [2.合并](#2合并)
      - [3.常用指令](#3常用指令)
  - [二、高阶功能](#二高阶功能)
    - [1. Amend——提交改写](#1-amend提交改写)
    - [2.Branch——分支](#2branch分支)
    - [3. Merge Branch——合并分支](#3-merge-branch合并分支)
    - [4. Stash——暂存](#4-stash暂存)
    - [5. Rebase——变基](#5-rebase变基)
    - [6.Checkout——签出功能](#6checkout签出功能)
    - [7.Undoing——撤销操作](#7undoing撤销操作)
    - [8. 图形化Git客户端](#8-图形化git客户端)
    - [常用操作](#常用操作)

<!-- /TOC -->

---
# 1. Git 简介

Git是一个开源的**分布式**版本控制系统，用于敏捷高效地处理任何或小或大的项目。

Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。

Git 与常用的版本控制工具 SVN（subversion），CVS等不同，它采用了分布式版本库的方式，不必服务器端软件支持。

- **Git 把内容按元数据方式存储**；
- **Git 没有一个全局的版本号**；
- **Git 的内容存储使用的是 SHA-1 哈希算法**。这能确保代码内容的完整性，确保在遇到磁盘故障和网络问题时降低对版本库的破坏。

![image-20210419205822992](C:\Users\34123\AppData\Roaming\Typora\typora-user-images\image-20210419205822992.png)



---

## 基础功能

在编写代码时，希望保存不同的代码版本，当软件出现bug时，可以回溯到之前的状态，比较版本之间的差别，从而找出bug的源头。此外，在多人分工协作的时候，也经常修改到相同的文件，此时若有一个工具可以帮助完成修改的合并，就可以帮助我们节省不少的时间。版本控制系统应运而生！

Git就是版本控制工具之一，其适用于中小项目的开发。

GitKraken是一个图形化客户端，比较适合入门。

---
### 1.创建提交
在本地仓库中添加代码或增删修改文件之后，GitKraken界面中，会出现WIP的提示，这表示“正在施工中”（working in progress），点击之后，右侧边栏中看到多出的或者修改的文件列表。点击可查看修改的内容。

提交步骤：点击Stage，填写commit信息，然后点击commit提交。如果要同步到远程服务器，需要使用push功能。origin是指默认的远程服务器。

---
### 2.合并
可以使用Pull功能，将远程仓库的提交合并到本地仓库。此时，修改已经自动合并。如果同时修改一段代码，则会提示冲突（Git 不止如何合并），这时就需要手动处理冲突！修改之后，重新commit

---
### 3.常用指令
1. 配置用户基本信息：
`git config --global user.name <用户名>`
`git config --global user.email <邮箱>`
2. 创建一个新仓库：`git init`
3. 从远程服务器克隆一个仓库：`git clone <远程仓库的 Url>`
4. 显示当前的工作目录下的提交文件状态：`git status`
5. 将指定文件Stage（标记为将要被提交的文件）：`git add <文件路径>`
6. 将指定恩建Unstage（取消标记为将要被提交的文件）：`git reset <文件路径>`
7. 创建一个提交并提供提交信息：`git commit -m “提交信息”`
8. 显示提交历史：`git log`
9. 向远程仓库推送（Push）：`git push`

---
## 高阶功能

 ![image-20210404191458714](D:\Github\ROS-Learning\imgs\image-20210404191458714.png)

### 1. Amend——提交改写

有时在完成提交后会发现提交中的代码有误，或者提交信息有误。amend可以用来对已提交的文件或者提交信息进行修改，最好对只对本地的提交使用。使用方法为：当发现提交错误后，再按照之前的步骤再次提交，只不过需要勾选amend，这个提交并不会创建一个新的提交，而只是修改之前已经存在的提交。

---

### 2.Branch——分支

有时不确定自己修改的代码是否有bug，其次我们也不希望这个实验性的功能出现在软件的发布版本上，因为很可能这个功能并不实用。此时可以使用Git中的分支功能将软件发布版本和实验性功能区分开来，Branch之间不会相互影响。

---

### 3. Merge Branch——合并分支

注意如果出现报错，则需要手动解决冲突。push操作默认只会推送master分支，如果想将其他分支进行推送，则需要单独进行push。

---

### 4. Stash——暂存

如果在修改当前分支的内容时，需要处理另一个分支的bug，则可以将当前的修改暂存起来。注意Stage和Stash虽然均可翻译为暂存，但是它们的功能则完全不同。

GitKraken中的操作：首先点击Stash，然后在左侧边栏中可以发现有Stash这一栏；之后进行其它分支的操作，当操作完成后，再点击Pop按钮，恢复之前正在进行的修改。

---

### 5. Rebase——变基

与merge不同的是，rebase在合并分支的过程中，会直接将整个分支取下来，嫁接在另一个分支上，由于改变了原有分支的基底，这也是名字变基的由来。通过变基得到的提交历史不会出现分叉，看起来简洁直观。变基之后的历史呈现一条直线，非常直观。

使用merge提交，原先的提交的提交历史会被完全保留，

---

### 6.Checkout——签出功能

恢复代码之前的版本完成bug的修复，此时checkout就派上用场了。注意HEAD指向的是当前提交，之前因为我们都在main和test分支下工作，HEAD指向的自然就是main分支和test分支自己。由于目前我们已经是脱离分支的状态，而HEAD在这里就代表我们当前正处于的这个提交。

完成修改之后，可以创建一个新的commit，然后使用左侧边栏中，右击main分支，选择Fast-Forward to main，使HEAD指向main。

---

### 7.Undoing——撤销操作

如果你在Git中提交了代码或者错误合并了一个分支，可以使用undoing操作。在Git中的每一次操作都被记录在称为reflog的文件里，利用它可以轻松帮你回退到之前的状态。

在GitKraken中，可以直接点击undo按钮，实现撤销操作！如果已经提交到远程服务器，那么这个操作无效。

注意，不要修改远程仓库的提交历史，因为所有开发者都为护着同一个开发历史，如果自己擅自修改之后，别人的记录就对不上了。

撤销已经提交的代码，可以使用Git中的revert功能，在提交上右击，选择revert commit。可以看到生成了一个新的commit，这说明Git没有去修改原来的提交历史，而是生成了一个与之前提交完全相反的新提交。

---

### 8. 图形化Git客户端

- SourceTree
- SmartGit
- TortoiseGit

---

### 常用操作

1. 修改（Amend）上一个提交：

   `git commit --amend -m "<新提交信息>"`

2. 查案所有分支：`git branch`

3. 创建新分支：`git branch <分支名字>`

4. 切换分支：`git checkout <分支名字>`

5. 重命名分支：`git branch -m <旧名字><新名字>`
6. 删除分支：`git branch -d <分支名字>`
7. 将分支变基（Rebase）到main（需要先切换到分支之后，再完成变基）：
`git checkout <分支名字>`
`git rebase main`
8. 使用快进（Fast-Forward将分支合并到master）：
`git checkout <分支名字>`
`git merge --ff-only `
9. 中止这一次提交的合并（当遇到冲突时）：`git merge --abort`
10. 将未提交的修改暂存（Stash）：`git stash save "<可以输入一个信息>"`
11. 将上一个暂存的修改恢复并从暂存列表中删除：`git stash pop`
12. 签出指定的提交：`git checkout <提交的hash>`
13. 撤销旧提交：`git revert <旧提交的hash>`
14. 利用reflog查看本地仓库中的所有操作：`git reflog`

---
> Ref:
>
> 1. Git 官方文档：https://git-scm.com/doc
> 2. [Git + GitHub 10分钟完全入门（video）](https://www.bilibili.com/video/BV1KD4y1S7FL/?spm_id_from=333.788.recommend_more_video.-1)
> 3. [Git 进阶教程（video）](https://www.bilibili.com/video/BV1hA411v7qX)
> 4. [Git 教程](https://www.runoob.com/git/git-tutorial.html)
