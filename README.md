# ROS-Learning
The current repository mainly includes knowledge about linux shell and robot operating system (ROS).

机器人操作系统学习笔记。

---
> Contributer: datamonday
>
> Github Repo: https://github.com/datamonday/ROS-Learning

---
<!-- TOC -->

- [ROS-Learning](#ros-learning)
- [01. Git Basic Usage](#01-git-basic-usage)   
- [02. Vim Basic Usage](#02-vim-basic-usage)   
- [03. Shell Basic Usage](#03-shell-basic-usage)
- [04. Linux Tutorial Notes](#04-linux-tutorial-notes) 
- [05. ROS Introduction](#05-ros-introduction) 
- [06. ROS Tutorial Notes](#06-ros-tutorial-notes)

<!-- /TOC -->

---
## 01. Git Basic Usage
<!-- TOC -->

- [1. Git 简介](#1-git-简介)
- [2. Git 工作流程](#2--git-工作流程)
- [3. Git 基本概念](#3-git-基本概念)
- [4. Git 创建仓库](#4-git-创建仓库)
  - [4.1 git init](#41-git-init)
  - [4.2 git clone](#42-git-clone)
  - [4.3 git config](#43-git-config)
- [5. Git 基本操作](#5-git-基本操作)
- [6. Git 分支管理](#6-git-分支管理)
  - [6.1 `branch` 列出/创建分支](#61-branch-列出创建分支)
  - [6.2 `checkout` 切换分支](#62-checkout-切换分支)
  - [6.3 `branch -d` 删除分支](#63-branch--d-删除分支)
  - [6.4 `merge` 合并分支](#64-merge-合并分支)
  - [6.5 合并冲突](#65-合并冲突)
- [7. `log` 查看提交历史](#7-log-查看提交历史)
- [8. Git 标签](#8-git-标签)
- [9. Git 服务器搭建](#9-git-服务器搭建)
  - [9. 1 安装Git](#9-1-安装git)
  - [9. 2 创建证书登录](#9-2-创建证书登录)
  - [9.3 初始化Git仓库](#93-初始化git仓库)
  - [9.4 克隆仓库](#94-克隆仓库)
- [10. Github 使用](#10-github-使用)
  - [10.1 基础功能](#101-基础功能)
  	- [1）创建提交](#1创建提交)
  	- [2）合并](#2合并)
  	- [3）常用指令](#3常用指令)
  - [10.2 高阶功能](#102-高阶功能)
  	- [1）Amend——提交改写](#1-amend提交改写)
  	- [2）Branch——分支](#2branch分支)
  	- [3）Merge Branch——合并分支](#3-merge-branch合并分支)
  	- [4）Stash——暂存](#4-stash暂存)
    - [5）Rebase——变基](#5-rebase变基)
  	- [6）Checkout——签出功能](#6checkout签出功能)
    - [7）Undoing——撤销操作](#7undoing撤销操作)
  	- [8）图形化Git客户端](#8-图形化git客户端)   
  - [10.3 常用操作](#常用操作)

<!-- /TOC -->

---
## 02. Vim Basic Usage
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

---
## 03. Shell Basic Usage


---
## 04. Linux Tutorial Notes

<!-- /TOC -->

- [1. Linux 系统目录结构](#1-linux-系统目录结构)    
  - [1.1. 树状目录结构](#11-树状目录结构)   
  - [1.2. 重要系统目录](#12-重要系统目录)   
- [2. Linux 系统启动过程](#2-linux-系统启动过程)   
  - [2.1. 内核引导](#21-内核引导)   
  - [2.2. 运行 init](#22-运行-init)      
    - [2.2.1. 运行级别](#221-运行级别)   
  - [2.3. 系统初始化](#23-系统初始化)   
  - [2.4. 建立终端](#24-建立终端)   
  - [2.5. 用户登录](#25-用户登录)     
    - [2.5.1. 图形与文字模式切换](#251-图形与文字模式切换)     
    - [2.5.2. 关机命令与流程](#252-关机命令与流程) 
- [3. 文件基本属性](#3-文件基本属性)   
  - [3.1. 文件权限组合表示](#31-文件权限组合表示)   
  - [3.2. 文件属主和属组](#32-文件属主和属组)   
  - [3.3. 更改文件属性](#33-更改文件属性)     
    - [3.3.1. chgrp：更改文件属组](#331-chgrp更改文件属组)     
    - [3.3.2. chown：更改文件属主](#332-chown更改文件属主)     
    - [3.3.3. chmod：更改文件9个属性](#333-chmod更改文件9个属性)     
    - [3.3.4. 符号类型改变文件权限](#334-符号类型改变文件权限) 
- [4. 文件与目录管理](#4-文件与目录管理)   
  - [4.1. 处理目录常用命令](#41-处理目录常用命令)     
    - [4.1.1. ls (列出目录)](#411-ls-列出目录)     
    - [4.1.2. cd (切换目录)](#412-cd-切换目录)     
    - [4.1.3. pwd (显示当前所在目录)](#413-pwd-显示当前所在目录)     
    - [4.1.4. mkdir (创建新目录)](#414-mkdir-创建新目录)     
    - [4.1.5. rmdir (删除空的目录)](#415-rmdir-删除空的目录)     
    - [4.1.6. cp (复制文件或目录)](#416-cp-复制文件或目录)     
    - [4.1.7. rm (移除文件或目录)](#417-rm-移除文件或目录)     
    - [4.1.8. mv (移动文件与目录，或修改名称)](#418-mv-移动文件与目录或修改名称)     
    - [4.1.9. ln (创建链接)](#419-ln-创建链接)     
    - [4.1.10. which (查找文件)](#4110-which-查找文件)     
    - [4.1.11. whereis (指定查找命令)](#4111-whereis-指定查找命令)     
    - [4.1.12. touch (修改时间属性)](#4112-touch-修改时间属性)   
  - [4.2. 文件内容查看命令](#42-文件内容查看命令)     
    - [4.2.1. cat (正序显示内容)](#421-cat-正序显示内容)     
    - [4.2.2. tac (倒序显示内容)](#422-tac-倒序显示内容)     
    - [4.2.3. nl (显示行号)](#423-nl-显示行号)     
    - [4.2.4. more (一页一页翻动)](#424-more-一页一页翻动)     
    - [4.2.5. less (一页一页翻动)](#425-less-一页一页翻动)     
    - [4.2.6. head (取文件前面几行)](#426-head-取文件前面几行)     
    - [4.2.7. tail (取文件后面几行)](#427-tail-取文件后面几行)     
    - [4.2.8. wc (统计文档字数)](#428-wc-统计文档字数)     
    - [4.2.9. look (查询单词)](#429-look-查询单词)   
  - [4.3. 软链接与硬链接](#43-软链接与硬链接) 
- [5. 用户和用户组管理](#5-用户和用户组管理)   
  - [5.1. 用户账号的管理](#51-用户账号的管理)     
    - [5.1.1. ）`useradd` 添加用户](#511-useradd-添加用户)     
    - [5.1.2. ）`userdel` 删除用户](#512-userdel-删除用户)     
    - [5.1.3. ）`usermod` 修改账号](#513-usermod-修改账号)     
    - [5.1.4. ）`passwd` 用户口令管理](#514-passwd-用户口令管理)   
  - [5.2. 用户组的管理](#52-用户组的管理)     
    - [5.2.1. ）`groupadd` 增加新用户组](#521-groupadd-增加新用户组)     
    - [5.2.2. ）`groupdel` 删除已有用户组](#522-groupdel-删除已有用户组)     
    - [5.2.3. ）`groupmod` 修改用户组属性](#523-groupmod-修改用户组属性)     
    - [5.2.4. ）`newgrp` 切换用户组](#524-newgrp-切换用户组)   
  - [5.3. 与用户账号有关的系统文件](#53-与用户账号有关的系统文件)     
    - [5.3.1. ）`/etc/passwd`](#531-etcpasswd)     
    - [5.3.2. ）`/etc/shadow`](#532-etcshadow)     
    - [5.3.3. ）`/etc/group`](#533-etcgroup)     
    - [5.3.4. ）添加批量用户](#534-添加批量用户) 
- [6. 磁盘管理](#6-磁盘管理)   
  - [6.1. df 检查文件系统的磁盘使用](#61-df-检查文件系统的磁盘使用)   
  - [6.2 du 检查文件和目录磁盘使用](#62-du-检查文件和目录磁盘使用)   
  - [6.3 fdisk 磁盘分区表](#63-fdisk-磁盘分区表)   
  - [6.4 mkfs 磁盘格式化](#64-mkfs-磁盘格式化)   
  - [6.5 fsck 磁盘检验](#65-fsck-磁盘检验)  
  - [6.6 mount 磁盘挂载与卸载](#66-mount-磁盘挂载与卸载) 

<!-- /TOC -->

---

## 05. ROS Introduction

> Ref:
>
> 1. []()

---

## 06. ROS Tutorial Notes

> Ref:
>
> 1. []()

---

