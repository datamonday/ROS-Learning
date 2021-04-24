<!-- TOC -->

- [1. Vim 介绍](#1-vim-介绍)
- [2. Vim 的三种模式](#2-vim-的三种模式)
  - [2.1. 命令模式 (Command mode)](#21-命令模式-command-mode)
  - [2.2. 输入模式 (Insert mode)](#22-输入模式-insert-mode)
  - [2.3. 底线命令模式 (Last line mode)](#23-底线命令模式-last-line-mode)
- [3. Vim 按键说明](#3-vim-按键说明)
  - [3.1. 命令模式按键操作](#31-命令模式按键操作)
  - [3.2. 输入模式按键操作](#32-输入模式按键操作)
  - [3.3. 底线命令模式按键操作](#33-底线命令模式按键操作)
- [4. Vim 实例](#4-vim-实例)
  - [4.1. 基本使用](#41-基本使用)
  - [4.2. 配置文件 vimrc](#42-配置文件-vimrc)
  - [4.3. 常用命令](#43-常用命令)
- [5. Vim 扩展](#5-vim-扩展)
  - [5.1. 代码自动补全](#51-代码自动补全)
  - [5.2. 插件配置](#52-插件配置)
  - [5.3. 插件删除](#53-插件删除)
  - [5.4. 插件 colorscheme](#54-插件-colorscheme)

<!-- /TOC -->



# 1. Vim 介绍

Vim是从 vi 发展出来的一个文本编辑器。官方网站 ([http://www.vim.org](http://www.vim.org/)) 介绍 vim 是一个程序开发工具。代码补全、编译及错误跳转等方便编程的功能特别丰富，在程序员中被广泛使用。

![vi-vim-cheat-sheet-sch](./imgs/vi-vim-cheat-sheet-sch.gif)

# 2. Vim 的三种模式

基本上 vi/vim 共分为三种模式，分别是**命令模式（Command mode）**，**输入模式（Insert mode）**和**底线命令模式（Last line mode）**。

![img](./imgs/vim-vi-workmodel.png)

## 2.1. 命令模式 (Command mode)

启动 vim 后，进入命令模式。此状态下敲击键盘被识别为命令，而非输入字符。比如此时按下 **<button>i</button>**，并不会输入一个字符，而是被当作一个命令。

以下是常用的几个命令：

- **<button>i</button>** 切换到输入模式，以输入字符。
- **<button>x</button>** 删除当前光标所在处的字符。
- **<button>:</button>** 切换到底线命令模式，以在最底一行输入命令。

若想要编辑文本：启动Vim，进入了命令模式，按下 <button>i</button>，切换到输入模式。

命令模式只有一些最基本的命令，因此仍要依靠**底线命令模式输入更多命令**。

## 2.2. 输入模式 (Insert mode)

在命令模式下，按 **<button>i</button>** 进入输入模式。在输入模式中，可以使用以下按键：

- **<button>字符按键</button> + <button>Shift</button>**，输入字符
- **<button>ENTER</button>**，回车键，换行
- **<button>BACK SPACE</button>**，退格键，删除光标前一个字符
- **<button>DEL</button>**，删除键，删除光标后一个字符
- **<button>方向键</button>**，在文本中移动光标
- **<button>HOME/END</button>**，移动光标到行首/行尾
- **<button>Page Up/Page Down</button>**，上/下翻页
- **<button>Insert</button>**，切换光标为输入/替换模式，光标将变成竖线/下划线
- **<button>ESC</button>**，退出输入模式，切换到命令模式

## 2.3. 底线命令模式 (Last line mode)

在命令模式下，按 **<button>:</button>** 键进入底线命令模式。

底线命令模式可以输入单个或多个字符的命令，可用的命令非常多。

在底线命令模式中，基本的命令有（已经省略了冒号）：

- **<button>q</button>** 退出程序
- **<button>w</button>** 保存文件

按ESC键可随时退出底线命令模式。

---

# 3. Vim 按键说明

## 3.1. 命令模式按键操作

| 移动光标的方法                                          |                                                              |
| :------------------------------------------------------ | ------------------------------------------------------------ |
| h 或 向左箭头键(←)                                      | 光标向左移动一个字符                                         |
| j 或 向下箭头键(↓)                                      | 光标向下移动一个字符                                         |
| k 或 向上箭头键(↑)                                      | 光标向上移动一个字符                                         |
| l 或 向右箭头键(→)                                      | 光标向右移动一个字符                                         |
| hjkl 是排列在一起的，因此可以使用这四个按钮来移动光标。 | 如果想要进行多次移动，例如向下移动 30 行，可以使用 <button>30j</button> 或 <button>30↓</button> 的组合按键， 即加上想要进行的次数(数字)后，按下动作即可！ |
| [Ctrl] + [f]                                            | 屏幕『向下』移动一页，相当于 [Page Down]按键 (常用)          |
| [Ctrl] + [b]                                            | 屏幕『向上』移动一页，相当于 [Page Up] 按键 (常用)           |
| [Ctrl] + [d]                                            | 屏幕『向下』移动半页                                         |
| [Ctrl] + [u]                                            | 屏幕『向上』移动半页                                         |
| +                                                       | 光标移动到非空格符的下一行                                   |
| -                                                       | 光标移动到非空格符的上一行                                   |
| <button>数字 n</button> + <button>space</button>        | 光标会向右移动这一行的 n 个字符。例如 <button>20</button> + <button>space</button> 光标会向后移动 20 个字符 |
| <button>0</button> 或 <button>Home</button>             | 光标移动到这一行最前面字符处                                 |
| <button>$</button> 或 <button>End</button>              | 光标移动到这一行最后面字符处                                 |
| H                                                       | 光标移动到屏幕最上方那一行的第一个字符                       |
| M                                                       | 光标移动到屏幕中央那一行的第一个字符                         |
| L                                                       | 光标移动到屏幕最下方那一行的第一个字符                       |
| <button>G</button>                                      | 移动到这个文档的最后一行                                     |
| nG                                                      | n 为数字。移动到这个文档的第 n 行。例如 20G 则会移动到这个文档的第 20 行(可配合 :set nu) |
| <button>gg</button>                                     | 移动到这个文档的第一行                                       |
| <button>数字n</button> + <button>Enter</button>         | 光标向下移动 n 行                                            |
| **搜索替换**                                            |                                                              |
| <button>/word</button>                                  | 向光标之下寻找一个名称为 word 的字符串。                     |
| <button>?word</button>                                  | 向光标之上寻找一个名称为 word 的字符串。                     |
| <button>按键 n</button>                                 | 重复前一个搜寻动作。举例来说， 如果刚刚执行 /word 去向下搜寻 word 这个字符串，则按下 n 后，会向下继续搜寻下一个名称为 word 的字符串。 |
| <button>按键N</button>                                  | 与 n 相反，为反向进行前一个搜寻动作。                        |
| /word 配合 n 及 N 使用                                  | 可以重复地找到一些想要搜寻的关键词！                         |
| :n1,n2s/word1/word2/g                                   | n1 与 n2 为数字。在第 n1 与 n2 行之间寻找 word1 这个字符串，并将该字符串取代为 word2 ！举例来说，在 100 到 200 行之间搜寻 vbird 并取代为 VBIRD 则： 『:100,200s/vbird/VBIRD/g』。(常用) |
| **:1,$s/word1/word2/g** 或 **:%s/word1/word2/g**        | 从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2 ！(常用) |
| **:1,$s/word1/word2/gc** 或 **:%s/word1/word2/gc**      | 从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2 ！且在取代前显示提示字符给用户确认 (confirm) 是否需要取代！(常用) |
| **删除、复制与粘贴**                                    |                                                              |
| <button>x</button> 或 <button>X</button>                | 在一行中，x 为向后删除一个字符，相当于 [del] 按键； X 为向前删除一个字符，相当于 [backspace]。 (常用) |
| <button>数字n</button> + <button>x</button>             | 连续向后删除 n 个字符。连续删除 10 个字符：『10x』。         |
| <button>dd</button>                                     | 删除光标所在的一整行(常用)                                   |
| <button>数字n</button> + <button>dd</button>            | n 为数字。删除光标所在的向下 n 行，例如 20dd 则是删除 20 行 (常用) |
| d1G                                                     | 删除光标所在行到第一行的所有数据                             |
| dG                                                      | 删除光标所在行到最后一行的所有数据                           |
| d$                                                      | 删除光标所在处到该行的最后一个字符                           |
| d0 (数字0)                                              | 删除光标所在处到该行的最前一个字符                           |
| <button>yy</button>                                     | 复制光标所在的一行                                           |
| <button>数字n</button> + <button>yy</button>            | 复制光标所在的向下 n 行，例如 20yy 则是复制 20 行            |
| y1G                                                     | 复制光标所在行到第一行的所有数据                             |
| yG                                                      | 复制光标所在行到最后一行的所有数据                           |
| y0                                                      | 复制光标所在的那个字符到该行行首的所有数据                   |
| y$                                                      | 复制光标所在的那个字符到该行行尾的所有数据                   |
| <button>p</button> 和 <button>P</button>                | p为将已复制的数据粘贴到光标下一行，P为贴在光标上一行！       |
| J                                                       | 将光标所在行与下一行的数据结合成同一行                       |
| c                                                       | 重复删除多个数据，例如向下删除 10 行，[ 10cj ]               |
| <button>u</button>                                      | 复原前一个动作。                                             |
| <button>Ctrl</button> + <button>r</button>              | 重做上一个动作。                                             |
| 这个 u 与 [Ctrl]+r 是很常用的指令！                     | 一个是 undo，另一个则是 redo                                 |
| <button>.</button>                                      | 重复前一个动作。 如果想要重复删除、重复粘贴等动作，按下小数点『.』即可 |

## 3.2. 输入模式按键操作

| 进入输入或取代的编辑模式                                     |                                                              |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| <button>i</button> 和 <button>I</button>                     | 进入输入模式(Insert mode)：<button>i</button> 为『从光标所在处输入』； <button>I</button> 为『从光标所在行的第一个非空格符处开始输入』。 |
| <button>a</button> 和 <button>A</button>                     | 进入输入模式(Insert mode)： <button>a</button> 为『从目前光标所在的下一个字符处开始输入』； <button>A</button> 为『从光标所在行的最后一个字符处开始输入』。 |
| <button>o</button> 和 <button>O</button>                     | 进入输入模式(Insert mode)： 这是英文字母 o 的大小写。<button>o</button> 为从光标所在的下一行处输入新的一行；<button>O</button> 为从光标所在的上一行处输入新的一行！ |
| <button>r</button> 和 <button>R</button>                     | 进入取代模式(Replace mode)： <button>r</button> 只取代光标所在的那一个字符一次；<button>R</button>会一直取代光标所在的文字，直到按下 ESC 为止！ |
| 上面这些按键中，在 vi 画面的左下角处会出现『--INSERT--』或『--REPLACE--』的字样。 |                                                              |
| <button>Esc</button>                                         | 退出编辑模式，回到一般模式                                   |

## 3.3. 底线命令模式按键操作

| 指令行的保存、离开等指令 |                                                              |
| :----------------------- | ------------------------------------------------------------ |
| <button>:w</button>      | 将编辑的数据写入硬盘文档                                     |
| <button>:w!</button>     | 若文件属性为『只读』时，强制写入该文档。能不能写入与用户对该文档的权限有关。 |
| <button>:q</button>      | 退出 vi                                                      |
| <button>:q!</button>     | 若曾修改过文档，又不想保存，使用 ! 为强制离开不保存文档。    |
| <button>!</button>       | 在 vi 中表示『强制』                                         |
| <button>:wq</button>     | 保存后离开，若为 <button>:wq!</button> 则为强制保存后离开    |
| ZZ                       | 如果修改过，保存当前文件，然后退出！效果等同于保存并退出     |
| <button>ZQ</button>      | 不保存，强制退出。效果等同于 <button>**:q!**</button>。      |
| :w [filename]            | 将编辑的数据另存为名为 filename 的文档                       |
| :r [filename]            | 在编辑的数据中，读入另一个文档的数据。即将名为 filename 的文档内容加到游标所在行后面 |
| :n1,n2 w [filename]      | 将 n1 到 n2 的内容保存成名为 filename 的文档                 |
| :! command               | 暂时离开 vi 到命令行模式下执行 command 的显示结果！例如 <button>:! ls /home</button> 可在 vi 当中查看 /home 下以 ls 输出的文档信息！ |
| vim 环境变更             |                                                              |
| :set nu                  | 显示行号，设定之后，会在每一行的前缀显示该行的行号           |
| :set nonu                | 与 set nu 相反，为取消行号！                                 |

注意：在 vi/vim 中，数字通常代表重复做几次的意思！ 也有可能是代表去到第几个什么什么的意思。

---
# 4. Vim 实例

## 4.1. 基本使用

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

## 4.2. 配置文件 vimrc

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

## 4.3. 常用命令

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

# 5. Vim 扩展

## 5.1. 代码自动补全

vim中代码自动补全只能是已经出现过的单词。

命令：<button> control </button> + <button> N </button>

---

## 5.2. 插件配置

 插件 vim plug 与 插件 vim awesome 可以实现 node tree：

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

## 5.3. 插件删除

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
## 5.4. 插件 colorscheme

---
> Reference:
>
> 1. [vim入门教程（video）](https://www.bilibili.com/video/BV1Yt411X7mu)
> 2. [vim使用教程（blog）](https://www.runoob.com/linux/linux-vim.html)
