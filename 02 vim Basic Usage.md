<!-- TOC -->

- [1. 基本使用](#1-基本使用) 
- [2. 编辑配置文件 vimrc](#2-编辑配置文件-vimrc)  
- [3. 常用命令](#3-常用命令)  
- [4. 代码自动补全](#4-代码自动补全)
	- [4.1 插件 vim plug](#41-插件-vim-plug)
	- [4.2 插件 vim awesome](#42-插件-vim-awesome)
	- [4.3 插件删除](#43-插件删除)  
	- [4.4 插件 vim colorscheme](#44-插件-vim-colorscheme)

<!--/TOC -->

---
# Vim

![vi-vim-cheat-sheet-sch](D:\Github\ROS-Learning\imgs\vi-vim-cheat-sheet-sch.gif)

![img](D:\Github\ROS-Learning\imgs\vim-vi-workmodel.png)

---
## 1. 基本使用

使用 vim 编辑文件：

```shell
vim filename
```

---

1.两种命令模式：

- command（命令模式）；
- edit （编辑模式）（按 <button> i </button> 键进入）；

---

2.保存退出：

- 按下 <button> ESC </button> 之后，输入 <button>: </button>+<button> w </button>+<button> q </button>

---

3.语法高亮：

- 命令模式下，输入 <button>: </button>+<button>syntax on</button>

---

4.显示行号：

- 命令模式下，输入 <button>: </button>+<button>set number</button>

---

5.不保存退出：

- 按下 <button> ESC </button> 之后，输入 <button>: </button>+<button>q</button>+<button>!</button>

---

## 2. 编辑配置文件 vimrc

命令行输入：

```shell
vim ~/.vimrc
```

编辑内容：

```shell
syntax on
set number
```

保存退出，再次进入vim可见已经实现语法高亮和行号显示。



**如果不想从头配置，可以参考他人配置好的 vimrc 配置文件，例如**：

https://github.com/amix/vimrc/blob/master/vimrcs/basic.vim

---

## 3. 常用命令

1.移动光标：编辑模式下，<button>H</button> + <button>J</button> + <button> K </button> + <button> L </button> 可以当做方向键使用，分别代表 <button>←</button> + <button>↓</button> + <button> ↑</button> + <button> → </button> 。

2.跳词：编辑模式下，<button>W</button> 可以往后跳一个单词；<button>B</button> 可以往回跳一个单词。

3.翻页：编辑模式下，<button>page up</button> 和 <button>page down</button> 实现翻页；也可以分别使用：

- <button>control</button> + <button>B</button>
- <button>control</button> + <button>F</button>

4.跳到指定行：命令模式下，<button>指定行</button> + <button> gg </button>。

5.跳指定行数：命令模式下，<button>指定行数</button> + <button>j </button>。

6.如果打错命令，可以使用 <button>ESC</button> 退出！  

---

7.查找指定单词：<button>/</button> + <button>指定单词</button>；此时，按<button>N</button> 可实现向下跳转；<button>shift</button> + <button> N </button> 可实现向上跳转。

8.整行剪切（删除）：命令模式下，连按两次 <button>C</button>，并且此时会自动转入编辑模式；如果想撤回剪切操作，可以转入命令模式下，按下 <button> U </button> 即可。

9.连续删除两行：命令模式下，<button> C </button> + <button> 2</button> + <button> C</button>。

10.粘贴：命令模式，<button> P </button>；此时如果想要撤销，按 <button> U</button> 即可。

---

11.选中剪切操作：命令模式下，按 <button>V</button> 进入 visual模式，按 <button> ↓ </button> 进行选中，之后按 <button> C </button> 进行剪切操作，可以使用 <button> P </button> 进行粘贴。

12.选中复制操作：命令模式下，按 <button>V</button> 进入 visual模式，按 <button> ↓ </button> 进行选中，之后按 <button>YY</button> 进行复制，可以使用 <button> P </button> 进行粘贴。

---

## 4. 代码自动补全

vim中代码自动补全只能是已经出现过的单词。

命令：<button> control </button> + <button> N </button>

---

## 4.1 插件 vim plug



## 4.2 插件 vim awesome

上述两个插件实现 node tree：

打开命令行：

```shell
$ vim ~/.vimrc
```

在文件末尾插入：

```shell
call plug#begin()
	Plug 'scrooloose/nerdtree'
call plug#end()
```

保存并退出。

打开一个文件（例如 `vim code.cpp`），并在命令模式下输入：

```shell
PlugInstall
```

完成插件的安装。

打开文件，在命令模式下，输入：

```shell
:help NERDTree.txt
```

打开插件的帮助文档，找到 2.1. Global Command可以查看命令。

打开文件（直接使用命令 `vim`），在命令模式下，输入：

```shell
:NERDTree
```

查看文件夹目录结构。

移动光标，点击回车键，可以打开文件并查看（此时将窗口一分为二），要想跳回到原目录，可以使用：

<button>control</button> + <button> W </button>

---

## 4.3 插件删除

打开命令行：

```shell
$ vim ~/.vimrc
```

在文件末尾插入：

```shell
call plug#begin()
# 注释掉不想使用的插件或者直接删除
	#Plug 'scrooloose/nerdtree'
call plug#end()
```

保存并退出。

第二步，打开文件（直接使用命令 `vim`）并进入命令模式，输入：`:PlugClean` 即可完成删除。

---
## 4.4 插件 vim colorscheme

---
> Reference:
>
> 1. [vim入门教程（video）](https://www.bilibili.com/video/BV1Yt411X7mu)
> 2. [vim使用教程（blog）](https://www.runoob.com/linux/linux-vim.html)












