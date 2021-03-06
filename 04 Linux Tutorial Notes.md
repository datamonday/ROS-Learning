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

# 1. Linux 系统目录结构

查看linux文件目录。打开终端输入：

```shell
 ls / 
```

输出：

![image-20210421111902762](./imgs/image-20210421111902762.png)



## 1.1. 树状目录结构

![img](./imgs/d0c50-linux2bfile2bsystem2bhierarchy.jpg)

以下是对这些目录的解释：

- **/bin**：
  bin 是 Binaries (二进制文件) 的缩写，存放着最经常使用的命令。

- **/boot：**
  存放启动 Linux 时使用的一些核心文件，包括连接文件以及镜像文件。

- **/dev ：**
  dev 是 Device(设备) 的缩写，用于存放 Linux 的外部设备，Linux 中访问设备的方式和访问文件的方式相同。

- **/etc：**
  etc 是 Etcetera(等等) 的缩写，用于存放**所有系统管理所需要的配置文件和子目录**。

- **/home**：
  用户的主目录，Linux 中的每个用户都有一个自己的目录，一般该目录名是以用户的账号命名的，如上图中的 alice、bob 和 eve。

- **/lib**：
  lib 是 Library(库) 的缩写，用于存放系统最基本的动态连接共享库，**类似于 Windows 的 DLL 文件**。几乎所有的应用程序都需要用到这些共享库。

- **/lost+found**：
  默认为空，用于保存系统非法关机后的文件。

- **/media**：
  Linux 系统会把自动识别的设备挂载到这个目录下，例如U盘、光驱等。

- **/mnt**：
  用于临时挂载其他文件系统，例如挂载光驱，进入该目录就可以查看光驱中的内容。

- **/opt**：
  opt 是 optional(可选) 的缩写，用于存放主机额外安装的软件，默认为空。

- **/proc**：
  proc 是 Processes(进程) 的缩写，`/proc` 是一种**伪文件系统（即虚拟文件系统）**，存储的是当前内核运行状态的一系列特殊文件，这个目录**是一个虚拟的目录**，它是系统内存的映射，可以通过直接访问这个目录来获取系统信息。**这个目录的内容不在硬盘上而是在内存里**，可以直接修改里面的某些文件，比如可以通过下面的命令来屏蔽主机的ping命令，使别人无法ping你的机器：
  
```shell
  echo 1 > /proc/sys/net/ipv4/icmp_echo_ignore_all
```

- **/root**：
  该目录为系统管理员，也称作超级权限者的用户主目录。

- **/sbin**：
  s 表示 Super User ，sbin 是 Superuser Binaries (超级用户的二进制文件) 的缩写，用于存放系统管理员使用的系统管理程序。

- **/selinux**：
   这个目录是 Redhat/CentOS 所特有的目录，**Selinux 是一个安全机制，类似于 windows 的防火墙**，但是这套机制比较复杂，这个目录就是存放selinux相关的文件的。

- **/srv**：
   该目录存放一些服务启动之后需要提取的数据。

- **/sys**：

  该目录下安装了 2.6 内核中新出现的一个文件系统 sysfs 。该文件系统是内核设备树的一个直观反映。sysfs 文件系统集成了3种文件系统的信息：（1）针对进程信息的 proc 文件系统；（2）针对设备的 devfs 文件系统；（3）针对伪终端的 devpts 文件系统。当一个内核对象被创建时，对应的文件和目录也在内核对象子系统中被创建。

- **/tmp**：
  tmp 是 temporary 的缩写，存放临时文件。

- **/usr**：
   usr 是 **unix shared resources (共享资源)** 的缩写，用户的应用程序和文件都放在这个目录下，**类似于 windows 下的 program files 目录**。

- **/usr/bin：**
  系统用户使用的应用程序。

- **/usr/sbin：**
  超级用户使用的比较高级的管理程序和系统守护程序。

- **/usr/src：**
  内核源代码默认的放置目录。

- **/var**：
  var 是 variable 的缩写，用于存放经常被修改的目录。包括各种日志文件。

- **/run**：
  临时文件系统，存储系统启动以来的信息。当系统重启时，这个目录下的文件应该被删掉或清除。

---

## 1.2. 重要系统目录

在 Linux 系统中，有几个目录是比较重要的，平时需要注意不要误删除或者随意更改内部文件。

- **/etc**： 系统中的配置文件，如果更改了该目录下的某个文件可能会导致系统不能启动。

- **/bin, /sbin, /usr/bin, /usr/sbin**：系统预设的执行文件的放置目录，比如 ls 就是在 /bin/ls 目录下的。

  /bin, /usr/bin 是给系统用户使用的指令（除root外的普通用户），而/sbin, /usr/sbin 则是给 root 使用的指令。

- **/var**： 存放系统运行的程序产生的日志，具体在 /var/log 目录下。

---

在 Linux 或 Unix 操作系统中，所有的文件和目录都被组织成以一个根节点开始的倒置的树状结构。

文件系统的最顶层是由根目录开始的，系统使用 ` / ` 表示根目录。在根目录之下的既可以是目录，也可以是文件，而每一个目录中又可以包含子目录文件。如此反复就可以构成一个庞大的文件系统。

在Linux文件系统中有两个特殊的目录，一个用户所在的工作目录（当前目录），用一个点 `.` 表示；另一个是当前目录的上一级目录（父目录），用两个点 `..` 表示。

-  `.`   代表当前的目录，也可以用 `./` 表示；
- ` ..`  代表上一层目录，也可以用 `../` 表示。

如果一个目录或文件名以一个点 `.` 开始，表示这个目录或文件是一个隐藏目录或文件，如：.bashrc。即以默认方式查找时，不显示该目录或文件。可以在文件路径下使用 <button> ctrl </button> + <button> h </button> 显示隐藏的文件。

---

# 2. Linux 系统启动过程

Linux系统的启动过程可以分为5个阶段：

- 内核引导。
- 运行 init。
- 系统初始化。
- 建立终端 。
- 用户登录系统。

> init程序的类型：
>
> - **SysV：** init，CentOS 5之前，配置文件： /etc/inittab。
> - **Upstart：** init，CentOS 6，配置文件： /etc/inittab, /etc/init/*.conf。
> - **Systemd：**systemd，CentOS 7，配置文件： `/usr/lib/systemd/system`、 `/etc/systemd/system`。

---

## 2.1. 内核引导

按下计算机电源键之后，BIOS开机自检，按照BIOS中设置的启动设备来启动。当操作系统接管硬件之后，首先读入 `/boot` 目录下的内核文件。

![img](./imgs/bg2013081702.png)

## 2.2. 运行 init

init 进程是系统所有进程的起点，没有这个进程，系统中任何进程都不会启动。

init 进程首先读取配置文件 `/etc/inittab` 。

![img](./imgs/bg2013081703.png)

### 2.2.1. 运行级别

许多程序需要开机启动。它们在Windows叫做 **服务(service)**，在Linux叫做 **守护进程(daemon)**。

init进程的一大任务就是去运行这些开机启动的程序。但是，不同的场合需要启动不同的程序，比如用作服务器时，需要启动Apache，用作桌面就不需要。

Linux允许为不同的场合，分配不同的开机启动程序，这就叫做 **运行级别(runlevel)**。启动时需要根据运行级别确定要运行哪些程序。

![img](./imgs/bg2013081704.png)

Linux系统有7个运行级别(runlevel)：

- 运行级别0：系统停机状态，系统默认运行级别不能设为0，否则不能正常启动；
- 运行级别1：单用户工作状态，root权限，用于系统维护，禁止远程登陆；
- 运行级别2：多用户状态(没有NFS)；（*NFS* 即 Network File System）
- 运行级别3：完全的多用户状态(有NFS)，登陆后进入控制台命令行模式；
- 运行级别4：系统未使用，保留；
- 运行级别5：X11控制台，登陆后进入图形GUI模式；
- 运行级别6：系统正常关闭并重启，默认运行级别不能设为6，否则不能正常启动。

---

## 2.3. 系统初始化

在init的配置文件中有这么一行： 

```shell
si::sysinit:/etc/rc.d/rc.sysinit
```

它调用执行了 `/etc/rc.d/rc.sysinit`，而rc.sysinit是一个bash shell的脚本，主要完成一些系统初始化的工作，**`rc.sysinit`** 是每一个运行级别都要首先运行的重要脚本。它主要完成的工作有：**激活交换分区，检查磁盘，加载硬件模块**以及其它一些需要优先执行任务。

真正的rc启动脚本都存放于 `/etc/rc.d/init.d/` 目录下。

![img](./imgs/bg2013081705.png)

注：**rc** 取自 runcom，来自 MIT 在 1965 年发展的 CTSS系统。

其含义为：具有从档案中取出一系列命令来执行的功能，称为 run commands (runcom)，而这种档案又称为一个 runcom (a runcom)。

## 2.4. 建立终端

rc执行完毕后，返回init。此时基本系统环境已经设置好了，各种守护进程也已经启动了。

init 会打开6个终端，以便用户登录系统。在inittab中的以下6行就是定义了6个终端：

```shell
1:2345:respawn:/sbin/mingetty tty1
2:2345:respawn:/sbin/mingetty tty2
3:2345:respawn:/sbin/mingetty tty3
4:2345:respawn:/sbin/mingetty tty4
5:2345:respawn:/sbin/mingetty tty5
6:2345:respawn:/sbin/mingetty tty6
```

从上面可以看出在2、3、4、5的运行级别中都将以respawn方式运行mingetty程序，mingetty 程序（文本登录方式）能打开终端、设置模式。

同时它会显示一个文本登录界面，这个界面就是我们经常看到的登录界面，在这个登录界面中会提示用户输入用户名，而用户输入的用户将作为参数传给login程序来验证用户的身份。

------

## 2.5. 用户登录

一般来说，用户的登录方式有三种：

- 1）命令行登录
- 2）ssh登录
- 3）图形界面登录

![img](./imgs/bg2013081706.png)

运行级别为5的图形方式的用户通过图形化的登录界面登录。登录成功后可以直接进入 KDE、Gnome 等窗口管理器。

mingetty 程序是文本登录方式。Linux 的账号验证程序是 login，它接收 mingetty 传来的用户名作为用户名参数。然后对用户名进行分析：如果用户名不是 root，且存在 /etc/nologin 文件，login 将输出 nologin 文件的内容，然后退出。

此举是在系统维护时防止非root用户登录。只有/etc/securetty中登记了的终端才允许 root 用户登录，如果不存在这个文件，则 root 用户可以在任何终端上登录。/etc/usertty文件用于对用户作出附加访问限制，如果不存在这个文件，则没有其他限制。

------

### 2.5.1. 图形与文字模式切换

Linux预设提供了六个命令窗口终端机让用户登录。默认登录的是第一个窗口，也就是tty1。如果安装了图形界面，默认进入图形界面。六个窗口分别为tty1,tty2 … tty6，可以通过 <button>Ctrl</button> + <button>Alt</button> + <button>F1 ~ F6</button> 进行切换。

如果进入命令窗口界面后想再返回图形界面，只要按 Ctrl + Alt + F7 即可。

如果为 vmware 虚拟机，命令窗口切换的快捷键为 Alt + Space + F1~F6。如果在图形界面下，则可以通过 Alt + Shift + Ctrl + F1~F6 切换至命令窗口。

![img](./imgs/bg2013081707.png)

------

### 2.5.2. 关机命令与流程

在linux领域内大多用在服务器上，很少遇到关机的操作。毕竟服务器上跑一个服务是永无止境的，除非特殊情况下，不得已才会关机。

正确的关机流程为：`sync > shutdown > reboot > halt`。

关机指令为：`shutdown`，可以通过 `man shutdown` 查看帮助文档。

运行如下命令关机：

```shell
sync 将数据由内存同步到硬盘。

shutdown 关机指令

shutdown –h 10  将在10分钟后关机
shutdown –h now 立马关机
shutdown –h 20:25 系统会在今天20:25关机
shutdown –h +10 十分钟后关机
shutdown –r now 系统立马重启
shutdown –r +10 系统十分钟后重启

reboot 重启，等同于 shutdown –r now

halt 关闭系统，等同于 shutdown –h now 和 poweroff
```

**不管是重启系统还是关闭系统，首先要运行 `sync` 命令，把内存中的数据写到磁盘中。**

关机命令：**`shutdown –h now halt poweroff`** 、 **`init 0`**

重启命令：**`shutdown –r now reboot init 6`**。

---

halt 命令通知硬件来停止所有的 CPU 功能，但是仍然保持通电。你可以用它使系统处于低层维护状态。注意在有些情况会它会完全关闭系统。

```shell
# halt             ### 停止机器
# halt -p          ### 关闭机器、关闭电源
# halt --reboot    ### 重启机器
```

poweroff 会发送一个 ACPI 信号来通知系统关机。

```shell
# poweroff           ### 关闭机器、关闭电源
# poweroff --halt    ### 停止机器
# poweroff --reboot  ### 重启机器
```

reboot 命令 reboot 通知系统重启。

```shell
# reboot           ### 重启机器
# reboot --halt    ### 停止机器
# reboot -p        ### 关闭机器
```

---

# 3. 文件基本属性

Linux 系统是一种典型的多用户系统，不同的用户处于不同的地位，拥有不同的权限。为了保护系统的安全性，Linux 系统对不同的用户访问同一文件（包括目录文件）的权限做了不同的规定。

通常使用以下两个命令来修改文件或目录的所属用户与权限：

- `chown` (change ownerp) ： 修改所属用户与组。
- `chmod` (change mode) ： 修改用户的权限。

下图中通过 chown 来授权用户，通过 chmod 为用户设置可以开门的权限。

![img](./imgs/1_151733904241.png)

使用 **`ll`** 或者 **`ls –l`** 命令来显示一个文件的属性以及文件所属的用户和组，如：

![image-20210421131808811](./imgs/image-20210421131808811.png)



## 3.1. 文件权限组合表示

**bin** 文件的第一个属性用 **d** 表示。**d** 在 Linux 中代表该文件是一个目录文件。

在 Linux 中第一个字符代表这个文件是目录、文件或链接文件等等。

- 当为 **d** 则是**目录**；
- 当为 **-** 则是**文件**；
- 若是 **l** 则表示为**链接文档(link file)**；
- 若是 **b** 则表示为装置文件里面的**可供储存的接口设备(可随机存取装置)**；
- 若是 **c** 则表示为装置文件里面的**串行端口设备**，例如键盘、鼠标(一次性读取装置)。

接下来的字符中，以三个为一组，且均为 **rwx** 的三个参数的组合。其中， **r** 代表可读(read)、 **w** 代表可写(write)、 **x** 代表可执行(execute)。 注意，这三个权限的位置不会改变，如果没有权限，就会出现减号 **-** 而已。

![img](./imgs/file-llls22.jpg)

每个文件的属性由左边第一部分的 10 个字符来确定（如下图）。

![363003_1227493859FdXT](./imgs/363003_1227493859FdXT.png)

从左至右用 **0-9** 这些数字来表示。

第 **0** 位确定文件类型，第 **1-3** 位确定属主（该文件的所有者）拥有该文件的权限。第4-6位确定属组（所有者的同组用户）拥有该文件的权限，第7-9位确定其他用户拥有该文件的权限。

其中，第 **1、4、7** 位表示读权限，如果用 **`r`** 字符表示，则有读权限，如果用 **-** 字符表示，则没有读权限；第 **2、5、8** 位表示写权限，如果用 **`w`** 字符表示，则有写权限，如果用 **-** 字符表示没有写权限；第 **3、6、9** 位表示可执行权限，如果用 **`x`** 字符表示，则有执行权限，如果用 **-** 字符表示，则没有执行权限。

## 3.2. 文件属主和属组

```shell
datazero@ubuntu:~$ ls -l
total 64
drwxr-xr-x 2 root  root  4096 Feb 15 14:46 cron
drwxr-xr-x 3 mysql mysql 4096 Apr 21  2014 mysql
```

在Linux系统中，用户是按组分类的，一个用户属于一个或多个组。

文件所有者以外的用户又可以分为：文件所有者的同组用户和其他用户。

因此，Linux系统按文件所有者、文件所有者同组用户和其他用户来规定了不同的文件访问权限。

在以上实例中，mysql 文件是一个目录文件，属主和属组都为 mysql，属主有可读、可写、可执行的权限；与属主同组的其他用户有可读和可执行的权限；其他用户也有可读和可执行的权限。

对于 root 用户来说，一般情况下，文件的权限对其不起作用。

---

## 3.3. 更改文件属性

### 3.3.1. chgrp：更改文件属组

语法：

```shell
chgrp [-R] 属组名 文件名
```

参数选项

- -R：递归更改文件属组，就是在更改某个目录文件的属组时，如果加上-R的参数，那么该目录下的所有文件的属组都会更改。

### 3.3.2. chown：更改文件属主

也可以同时更改文件属组。

语法：

```shell
chown [–R] 属主名 文件名
chown [-R] 属主名：属组名 文件名
```

进入 /root 目录（~）将install.log的拥有者改为bin这个账号：

```shell
datazero@ubuntu:~$ cd ~
datazero@ubuntu:~$ chown bin install.log
datazero@ubuntu:~$ ls -l
-rw-r--r--  1 bin users 68495 Jun 25 08:53 install.log
```

将install.log的拥有者与群组改回为root：

```shell
datazero@ubuntu:~$ chown root:root install.log
datazero@ubuntu:~$ ls -l
-rw-r--r--  1 root root 68495 Jun 25 08:53 install.log
```

### 3.3.3. chmod：更改文件9个属性

Linux文件属性有两种设置方法，一种是数字，一种是符号。

Linux 文件的基本权限就有九个，分别是 **owner/group/others(拥有者/组/其他)** 三种身份各有自己的 **read/write/execute** 权限。

文件的权限字符为： **`-rwxrwxrwx`** ， 这九个权限是三个三个一组的！**可以使用数字来代表各个权限**，各权限的位权对照表如下：

- r:4
- w:2
- x:1

每种身份(owner/group/others)各自的三个权限(r/w/x)的位权可以累加，例如权限 **`-rwxrwx---`** 的位权是：

- owner = rwx = 4+2+1 = 7
- group = rwx = 4+2+1 = 7
- others= --- = 0+0+0 = 0

所以设定权限的变更时，该文件的权限数字就是 **`770`**。变更权限的指令 chmod 的语法：

```shell
 chmod [-R] xyz 文件或目录
```

选项与参数：

- xyz : 就是刚刚提到的数字类型的权限属性，为 rwx 属性数值的相加。
- -R : 进行递归(recursive)的持续变更，亦即连同次目录下的所有文件都会变更

举例来说，如果要将 .bashrc 这个文件所有的权限都设定启用，那么命令如下：

```shell
datazero@ubuntu:~$ ls -al .bashrc
-rw-r--r--  1 root root 395 Jul  4 11:45 .bashrc
datazero@ubuntu:~$ chmod 777 .bashrc
datazero@ubuntu:~$ ls -al .bashrc
-rwxrwxrwx  1 root root 395 Jul  4 11:45 .bashrc
```

那如果要将权限变成 `-rwxr-xr--` 则位权为：`754`。

### 3.3.4. 符号类型改变文件权限

这是另一种改变权限的方法。可以使用 **u, g, o** 来代表三种身份的权限：

- user：用户
- group：组
- others：其他

此外， **a** 则代表 **all**，即全部的身份。读写的权限可以写成 **r, w, x**，也就是可以使用下表的方式来看：

| chmod | u g o a | +(加入) -(除去) =(设定) | r w x | 文件或目录 |
| ----- | ------- | ----------------------- | ----- | ---------- |
|       |         |                         |       |            |

如果将文件权限设置为 **`-rwxr-xr--`** ，可以使用 **`chmod u=rwx,g=rx,o=r 文件名`** 来设定:

```sh
datazero@ubuntu:~$ touch test1    // 创建 test1 文件
datazero@ubuntu:~$ ls -al test1   // 查看 test1 默认权限
-rw-r--r-- 1 root root 0 Nov 15 10:32 test1

datazero@ubuntu:~$ chmod u=rwx,g=rx,o=r  test1   // 修改 test1 权限

datazero@ubuntu:~$ ls -al test1
-rwxr-xr-- 1 root root 0 Nov 15 10:32 test1
```

而如果要将权限去掉而不改变其他已存在的权限呢？例如要拿掉全部用户的可执行权限，则：

```shell
datazero@ubuntu:~$ chmod  a-x test1
datazero@ubuntu:~$ ls -al test1
-rw-r--r-- 1 root root 0 Nov 15 10:32 test1
```

---

# 4. 文件与目录管理

Linux的目录结构为树状结构，最顶级的目录为根目录 /。

其他目录通过挂载可以将它们添加到树中，通过解除挂载可以移除它们。

- **绝对路径：**
  路径的写法，由根目录 **`/`** 写起，例如：`/usr/share/doc` 这个目录。
- **相对路径：**
  路径的写法，不是由 **`/`** 写起，例如由 `/usr/share/doc` 要到 `/usr/share/man` 底下时，可以写成： **`cd ../man`** 。

---

## 4.1. 处理目录常用命令

常见的处理目录命令：

- ls（英文全拼：list files）：列出目录及文件名；
- cd（英文全拼：change directory）：切换目录；
- pwd（英文全拼：print work directory）：显示目前的目录；
- mkdir（英文全拼：make directory）：创建一个新的目录；
- rmdir（英文全拼：remove directory）：删除一个空的目录；
- cp（英文全拼：copy file）：复制文件或目录；
- rm（英文全拼：remove）：删除文件或目录；
- mv（英文全拼：move file）：移动文件与目录，或修改文件与目录的名称。

可以使用 `man [命令]` 查看各个命令的使用文档，如 ：`man cp`。

---

### 4.1.1. ls (列出目录)

语法：

```shell
ls [-alrtAFR] [name...]
```

选项与参数：

- -a ：全部的文件，连同隐藏文件( 开头为 . 的文件) 一起列出；
- -d ：仅列出目录本身，而不是列出目录内的文件数据；
- -l ：长数据串列出，将文件型态、权限、拥有者、文件大小等资讯详细列出
- -r ：将文件以相反次序显示(原定依英文字母次序)
- -t ：将文件依建立时间之先后次序列出
- -A ：同 -a ，但不列出 "." (目前目录) 及 ".." (父目录)；
- -F ：在列出的文件名称后加一符号；例如可执行档则加 "*", 目录则加 "/"；
- -R ：若目录下有文件，则以下之文件亦皆依序列出。

将家目录下的所有文件列出来(含属性与隐藏档)

```shell
ls -al ~
```

---

### 4.1.2. cd (切换目录)

cd是Change Directory的缩写，用来变换工作目录。

语法：

```shell
 cd [相对路径或绝对路径]
```

### 4.1.3. pwd (显示当前所在目录)

pwd 是 **Print Working Directory** 的缩写，显示当前所在目录。

```shell
pwd [-P]
```

选项与参数：

- **-P** ：显示出确实的路径，而非使用连结 (link) 路径。

### 4.1.4. mkdir (创建新目录)

mkdir (make directory) 创建新的目录。

语法：

```shell
mkdir [-mp] 目录名称

mkdir -p test1/test2/test3/test4
```

选项与参数：

- -m ：配置文件的权限。
- -p ：递归创建所需要的目录(包含上一级目录)。

### 4.1.5. rmdir (删除空的目录)

语法：

```shell
 rmdir [-p] 目录名称
```

选项与参数：

- **-p ：**连同上一级『空的』目录也一起删除

### 4.1.6. cp (复制文件或目录)

cp 即拷贝文件和目录。

语法:

```shell
cp [-adfilprsu] 来源档(source) 目标档(destination)

cp [options] source1 source2 source3 .... directory
```

选项与参数：

- **-a：**相当於 -pdr 的意思，至於 pdr 请参考下列说明；
- **-d：**若来源档为连结档的属性(link file)，则复制连结档属性而非文件本身；
- **-f：**强制(force)，若目标文件已经存在且无法开启，则移除后再尝试一次；
- **-i：**若目标档(destination)已经存在时，在覆盖时会先询问；
- **-l：**进行硬式连结(hard link)的连结档创建，而非复制文件本身；
- **-p：**连同文件的属性一起复制过去，而非使用默认属性(备份常用)；
- **-r：**递归持续复制，用于目录的复制；
- **-s：**复制成为符号连结档 (symbolic link)，亦即『捷径』文件；
- **-u：**若 destination 比 source 旧才升级 destination ！

用 root 身份，将 root 目录下的 .bashrc 复制到 /tmp 下，并命名为 bashrc

```shell
cp ~/.bashrc /tmp/bashrc
cp -i ~/.bashrc /tmp/bashrc

# cp: overwrite `/tmp/bashrc'? n  <==n不覆盖，y为覆盖
```

### 4.1.7. rm (移除文件或目录)

语法：

```shell
 rm [-fir] 文件或目录
```

选项与参数：

- -f ：就是 force 的意思，忽略不存在的文件，不会出现警告信息；
- -i ：互动模式，在删除前会询问使用者是否动作
- -r ：递归删除啊！最常用在目录的删除了！这是非常危险的选项！！！

将刚刚在 cp 的实例中创建的 bashrc 删除掉！

```shell
rm -i bashrc

# rm: remove regular file `bashrc'? y
```

### 4.1.8. mv (移动文件与目录，或修改名称)

语法：

```shell
mv [-fiu] source destination
mv [options] source1 source2 source3 .... directory
```

选项与参数：

- -f ：如果目标文件已经存在，不会询问而直接覆盖；
- -i ：若目标文件 (destination) 已经存在时，会询问是否覆盖；
- -u ：若目标文件已经存在，且 source 比较新，才会升级 (update)

复制一文件，创建一目录，将文件移动到目录中

```shell
cd /tmp
cp ~/.bashrc bashrc

mkdir mvtest
mv bashrc mvtest
```

### 4.1.9. ln (创建链接)

Linux ln（英文全拼：link files）命令是一个非常重要命令，它的功能是为某一个文件在另外一个位置建立一个同步的链接。

当我们需要在不同的目录，用到相同的文件时，我们不需要在每一个需要的目录下都放一个必须相同的文件，我们只要在某个固定的目录，放上该文件，然后在 其它的目录下用ln命令链接（link）它就可以，不必重复的占用磁盘空间。

**语法**：

```shell
 $ ln [参数][源文件或目录][目标文件或目录]
```

其中参数的格式为

```shell
[-bdfinsvF] [-S backup-suffix] [-V {numbered,existing,simple}]

[--help] [--version] [--]
```

**命令功能** :

Linux文件系统中，有所谓的链接(link)，我们可以将其视为档案的别名，而链接又可分为两种 : 硬链接(hard link)与软链接(symbolic link)，硬链接的意思是一个档案可以有多个名称，而软链接的方式则是产生一个特殊的档案，该档案的内容是指向另一个档案的位置。硬链接是存在同一个文件系统中，而软链接却可以跨越不同的文件系统。

不论是硬链接或软链接都不会将原本的档案复制一份，只会占用非常少量的磁碟空间。

**软链接**：

- 1.软链接，以路径的形式存在。类似于Windows操作系统中的快捷方式
- 2.软链接可以 跨文件系统 ，硬链接不可以
- 3.软链接可以对一个不存在的文件名进行链接
- 4.软链接可以对目录进行链接

**硬链接**：

- 1.硬链接，以文件副本的形式存在。但不占用实际空间。
- 2.不允许给目录创建硬链接
- 3.硬链接只有在同一个文件系统中才能创建


---
**必要参数**：

- -b 删除，覆盖以前建立的链接
- -d 允许超级用户制作目录的硬链接
- -f 强制执行
- -i 交互模式，文件存在则提示用户是否覆盖
- -n 把符号链接视为一般目录
- -s 软链接(符号链接)
- -v 显示详细的处理过程

**选择参数**：

- -S "-S<字尾备份字符串> "或 "--suffix=<字尾备份字符串>"
- -V "-V<备份方式>"或"--version-control=<备份方式>"
- --help 显示帮助信息
- --version 显示版本信息

**实例**

给文件创建软链接，为log2013.log文件创建软链接link2013，如果log2013.log丢失，link2013将失效：

```shell
$ ln -s log2013.log link2013
```

---

### 4.1.10. which (查找文件)

Linux which命令用于查找文件。

which指令会在环境变量 $PATH 设置的目录里查找符合条件的文件。

**语法**

```shell
which [文件...]
```

**参数**：

- -n<文件名长度> ：指定文件名长度，指定的长度必须大于或等于所有文件中最长的文件名。
- -p<文件名长度> ：与-n参数相同，但此处的<文件名长度>包括了文件的路径。
- -w：指定输出时栏位的宽度。
- -V：显示版本信息。

**实例**

使用指令"which"查看指令"bash"的绝对路径，输入如下命令：

```shell
$ which bash
```

上面的指令执行后，输出信息如下所示：

```shell
/bin/bash    # bash可执行程序的绝对路径
```

### 4.1.11. whereis (指定查找命令)

Linux whereis命令用于查找文件。

该指令会在特定目录中查找符合条件的文件。这些文件应属于原始代码、二进制文件，或是帮助文件。

该指令只能用于查找二进制文件、源代码文件和man手册页，一般文件的定位需使用locate命令。

语法

```shell
whereis [-bfmsu][-B <目录>...][-M <目录>...][-S <目录>...][文件...]
```

**参数**：

-b 　只查找二进制文件。

-B<目录> 　只在设置的目录下查找二进制文件。

-f 　不显示文件名前的路径名称。

-m 　只查找说明文件。

-M<目录> 　只在设置的目录下查找说明文件。

-s 　只查找原始代码文件。

-S<目录> 　只在设置的目录下查找原始代码文件。

-u 　查找不包含指定类型的文件。

**实例**

使用指令"whereis"查看指令"bash"的位置，输入如下命令：

```shell
$ whereis bash 
```

上面的指令执行后，输出信息如下所示：

```shell
bash:/bin/bash/etc/bash.bashrc/usr/share/man/man1/bash.1.gz 
```

注意：以上输出信息从左至右分别为查询的程序名、bash路径、bash的man 手册页路径。

如果用户需要单独查询二进制文件或帮助文件，可使用如下命令：

```shell
$ whereis -b bash 
$ whereis -m bash 
```

输出信息如下：

```shell
$ whereis -b bash    # 显示bash 命令的二进制程序  
bash: /bin/bash /etc/bash.bashrc /usr/share/bash  # bash命令的二进制程序的地址  
$ whereis -m bash    # 显示bash 命令的帮助文件  
bash: /usr/share/man/man1/bash.1.gz  # bash命令的帮助文件地址
```

### 4.1.12. touch (修改时间属性)

Linux touch命令用于修改文件或者目录的时间属性，包括存取时间和更改时间。若文件不存在，系统会建立一个新的文件。

ls -l 可以显示档案的时间记录。

语法

```shell
touch [-acfm][-d<日期时间>][-r<参考文件或目录>] [-t<日期时间>][--help][--version][文件或目录…]
```

- **参数说明**：
- a 改变档案的读取时间记录。
- m 改变档案的修改时间记录。
- c 假如目的档案不存在，不会建立新的档案。与 --no-create 的效果一样。
- f 不使用，是为了与其他 unix 系统的相容性而保留。
- r 使用参考档的时间记录，与 --file 的效果一样。
- d 设定时间与日期，可以使用各种不同的格式。
- t 设定档案的时间记录，格式与 date 指令相同。
- --no-create 不会建立新档案。
- --help 列出指令格式。
- --version 列出版本讯息。

**实例**

使用指令"touch"修改文件"testfile"的时间属性为当前系统时间：

```shell
$ touch testfile   # 修改文件的时间属性 
```

使用ls命令查看testfile文件的属性：

```shell
$ ls -l testfile   # 查看文件的时间属性  
# 原来文件的修改时间为16:09  
-rw-r--r-- 1 hdd hdd 55 2011-08-22 16:09 testfile  
```

touch 修改文件属性以后，再次查看该文件的时间属性：

```shell
$ touch testfile  # 修改文件时间属性为当前系统时间  
$ ls -l testfile  # 查看文件的时间属性  
# 修改后文件的时间属性为当前系统时间  
-rw-r--r-- 1 hdd hdd 55 2011-08-22 19:53 testfile  
```

如果指定的文件不存在，则将创建一个新的空白文件。例如，在当前目录下，使用该指令创建一个空白文件"file"：

```shell
$ touch file    # 创建一个名为“file”的新的空白文件 
```

---

## 4.2. 文件内容查看命令

Linux系统中使用以下命令来查看文件的内容：

- cat 由第一行开始显示文件内容
- tac 从最后一行开始显示，可以看出 tac 是 cat 的倒着写！
- nl  显示的时候，顺道输出行号！
- more 一页一页的显示文件内容
- less 与 more 类似，但是比 more 更好的是，他可以往前翻页！
- head 只看头几行
- tail 只看尾巴几行

你可以使用 *man [命令]*来查看各个命令的使用文档，如 ：man cp。

### 4.2.1. cat (正序显示内容)

由第一行开始显示文件内容

语法：

```shell
$ cat [-AbEnTv]
```

选项与参数：

- -A ：相当于 -vET 的整合选项，可列出一些特殊字符而不是空白；
- -b ：列出行号，仅针对非空白行做行号显示，空白行不标行号！
- -E ：将结尾的断行字节 $ 显示出来；
- -n ：列印出行号，连同空白行也会有行号，与 -b 的选项不同；
- -T ：将 [tab] 按键以 ^I 显示出来；
- -v ：列出一些看不出来的特殊字符

检看 /etc/issue 这个文件的内容：

```shell
$ cat /etc/issue

CentOS release 6.4 (Final)
Kernel \r on an \m
```

### 4.2.2. tac (倒序显示内容)

tac与cat命令刚好相反，文件内容从最后一行开始显示，如：

```shell
$ tac /etc/issue

Kernel \r on an \m
CentOS release 6.4 (Final)
```

### 4.2.3. nl (显示行号)

语法：

```shell
$ nl [-bnw] 文件
```

选项与参数：

- -b ：指定行号指定的方式，主要有两种：
  -b a ：表示不论是否为空行，也同样列出行号(类似 cat -n)；
  -b t ：如果有空行，空的那一行不要列出行号(默认值)；
- -n ：列出行号表示的方法，主要有三种：
  -n ln ：行号在荧幕的最左方显示；
  -n rn ：行号在自己栏位的最右方显示，且不加 0 ；
  -n rz ：行号在自己栏位的最右方显示，且加 0 ；
- -w ：行号栏位的占用的位数。

实例一：用 nl 列出 /etc/issue 的内容

```shell
$ nl /etc/issue
     1  CentOS release 6.4 (Final)
     2  Kernel \r on an \m
```

### 4.2.4. more (一页一页翻动)

一页一页翻动

```shell
$ more /etc/man_db.config 
#
# Generated automatically from man.conf.in by the
# configure script.
#
# man.conf from man-1.6d
```

按键功能：

- 空格键：向下翻一页；
- Enter：向下翻『一行』；
- /字串：在显示的内容当中，向下搜寻『字串』这个关键字；
- :f      ：立刻显示出档名以及目前显示的行数；
- q      ：立刻离开 more ，不再显示该文件内容。
- b 或 [ctrl]-b ：往回翻页，不过这动作只对文件有用，对管线无用。

### 4.2.5. less (一页一页翻动)

一页一页翻动，以下实例输出/etc/man.config文件的内容：

```shell
$ less /etc/man.config
#
# Generated automatically from man.conf.in by the
# configure script.
#
# man.conf from man-1.6d
```

less运行时可以输入的命令有：

- 空白键  ：向下翻动一页；
- [pagedown]：向下翻动一页；
- [pageup] ：向上翻动一页；
- /字串   ：向下搜寻『字串』的功能；
- ?字串   ：向上搜寻『字串』的功能；
- n     ：重复前一个搜寻 (与 / 或 ? 有关！)
- N     ：反向的重复前一个搜寻 (与 / 或 ? 有关！)
- q     ：离开 less 这个程序。

### 4.2.6. head (取文件前面几行)

取出文件前面几行。

语法：

```shell
$ head [-n number] 文件 
```

选项与参数：

- -n ：后面接数字，表示显示几行。

```shell
$ head /etc/man.config
```

默认显示前面 10 行！显示前 20 行：

```shell
$ head -n 20 /etc/man.config
```

### 4.2.7. tail (取文件后面几行)

取出文件后面几行。

语法：

```shell
$ tail [-n number] 文件 
```

选项与参数：

- -n ：后面接数字，表示显示几行。
- -f ：表示持续侦测后面所接的档名，[ctrl]-c 结束tail的侦测。

```shell
$ tail /etc/man.config

# 默认的情况中，显示最后的十行！若要显示最后的 20 行，就得要这样：
$ tail -n 20 /etc/man.confi
```

### 4.2.8. wc (统计文档字数)

Linux wc命令用于计算字数。

利用wc指令我们可以计算文件的Byte数、字数、或是列数，若不指定文件名称、或是所给予的文件名为"-"，则wc指令会从标准输入设备读取数据。

**语法**

```shell
$ wc [-clw][--help][--version][文件...]
```

**参数**：

- -c或--bytes或--chars 只显示Bytes数。
- -l或--lines 显示行数。
- -w或--words 只显示字数。
- --help 在线帮助。
- --version 显示版本信息。

在默认的情况下，wc将计算指定文件的行数、字数，以及字节数：

```shell
$ wc testfile           # testfile文件的统计信息  
3 92 598 testfile       # testfile文件的行数为3、单词数92、字节数598 
```

其中，3 个数字分别表示testfile文件的行数、单词数，以及该文件的字节数。

如果想同时统计多个文件的信息，例如同时统计testfile、testfile_1、testfile_2，可使用如下命令：

```shell
wc testfile testfile_1 testfile_2   #统计三个文件的信息 
```

输出结果如下：

```shell
$ wc testfile testfile_1 testfile_2  # 统计三个文件的信息  
3 92 598 testfile  # 第一个文件行数为3、单词数92、字节数598  
9 18 78 testfile_1 # 第二个文件的行数为9、单词数18、字节数78  
3 6 32 testfile_2  # 第三个文件的行数为3、单词数6、字节数32  
15 116 708 总用量   # 三个文件总共的行数为15、单词数116、字节数708 
```

### 4.2.9. look (查询单词)

Linux look命令用于查询单词。输入欲查询的字首字符串，它会显示所有开头字符串符合该条件的单字。

**语法**

```shell
$ look [-adf][-t<字尾字符串>][字首字符串][字典文件]
```

**参数说明**：

- -a 使用另一个字典文件web2，该文件也位于/usr/dict目录下。
- -d 只对比英文字母和数字，其余一慨忽略不予比对。
- -f 忽略字符大小写差别。
- -t<字尾字符串> 设置字尾字符串。

查找testfile文件中以字母L开头的所有的行：

```shell
$ look L testfile 
```
原文件testfile中的内容如下：
```shell
$ cat testfile #查看testfile 文件内容  
HELLO LINUX!  
Linux is a free unix-type opterating system.  
This is a linux testfile!  
Linux test 
```
使用look命令查找以"L"开头的单词，结果如下：
```shell
$ look L testfile                              #查找以“L”开头的单词  
Linux is a free unix-type opterating system.   #第二行以“L”开头，列出全句  
Linux test                                     #第四行以“L”开头，列出全句 
```

---
## 4.3. 软链接与硬链接

inux 链接分两种，一种被称为硬链接（Hard Link），另一种被称为符号链接（Symbolic Link）。默认情况下，**ln** 命令产生硬链接。

**硬连接**

硬连接指通过索引节点来进行连接。在 Linux 的文件系统中，保存在磁盘分区中的文件不管是什么类型都给它分配一个编号，称为索引节点号(Inode Index)。在 Linux 中，多个文件名指向同一索引节点是存在的。比如：A 是 B 的硬链接（A 和 B 都是文件名），则 A 的目录项中的 inode 节点号与 B 的目录项中的 inode 节点号相同，即一个 inode 节点对应两个不同的文件名，两个文件名指向同一个文件，A 和 B 对文件系统来说是完全平等的。删除其中任何一个都不会影响另外一个的访问。

硬连接的作用是允许一个文件拥有多个有效路径名，这样用户就可以建立硬连接到重要文件，以防止“误删”的功能。其原因如上所述，因为对应该目录的索引节点有一个以上的连接。只删除一个连接并不影响索引节点本身和其它的连接，只有当最后一个连接被删除后，文件的数据块及目录的连接才会被释放。也就是说，文件真正删除的条件是与之相关的所有硬连接文件均被删除。

**软连接**

另外一种连接称之为符号连接（Symbolic Link），也叫软连接。软链接文件有类似于 Windows 的快捷方式。它实际上是一个特殊的文件。在符号连接中，文件实际上是一个文本文件，其中包含的有另一文件的位置信息。比如：A 是 B 的软链接（A 和 B 都是文件名），A 的目录项中的 inode 节点号与 B 的目录项中的 inode 节点号不相同，A 和 B 指向的是两个不同的 inode，继而指向两块不同的数据块。但是 A 的数据块中存放的只是 B 的路径名（可以根据这个找到 B 的目录项）。A 和 B 之间是“主从”关系，如果 B 被删除了，A 仍然存在（因为两个是不同的文件），但指向的是一个无效的链接。

```shell
$ touch f1          #创建一个测试文件f1
$ ln f1 f2          #创建f1的一个硬连接文件f2
$ ln -s f1 f3       #创建f1的一个符号连接文件f3
$ ls -li            # -i参数显示文件的inode节点信息
total 0
9797648 -rw-r--r--  2 oracle oinstall 0 Apr 21 08:11 f1
9797648 -rw-r--r--  2 oracle oinstall 0 Apr 21 08:11 f2
9797649 lrwxrwxrwx  1 oracle oinstall 2 Apr 21 08:11 f3 -> f1
```

从上面的结果中可以看出，硬连接文件 f2 与原文件 f1 的 inode 节点相同，均为 9797648，然而符号连接文件的 inode 节点不同。

```shell
$ echo "I am f1 file" >>f1
$ cat f1
I am f1 file

$ cat f2
I am f1 file

$ cat f3
I am f1 file

$ rm -f f1
$ cat f2
I am f1 file

$ cat f3
cat: f3: No such file or directory
```

通过上面的测试可以看出：**当删除原始文件 f1 后，硬连接 f2 不受影响，但是符号连接 f1 文件无效**。

结论：

-  1）删除符号连接f3，对f1，f2无影响；
-  2）删除硬连接f2，对f1，f3也无影响；
-  3）删除原文件f1，对硬连接f2没有影响，导致符号连接f3失效；
-  4）同时删除原文件f1，硬连接f2，整个文件会真正的被删除。

---

# 5. 用户和用户组管理

Linux系统是一个多用户多任务的分时操作系统，任何一个要使用系统资源的用户，都必须首先向系统管理员申请一个账号，然后以这个账号的身份进入系统。每个用户账号都拥有一个唯一的用户名和各自的口令。

实现用户账号的管理，要完成的工作主要有如下几个方面：

- 用户账号的添加、删除与修改。
- 用户口令的管理。
- 用户组的管理。

## 5.1. 用户账号的管理

用户账号的管理工作主要涉及到用户账号的添加、修改和删除。

添加用户账号就是在系统中创建一个新账号，然后为新账号**分配用户号、用户组、主目录和登录Shell等资源**。刚添加的账号是被锁定的，无法使用。

### 5.1.1. ）`useradd` 添加用户

添加新的用户账号使用 `useradd` 命令：

```shell
$ useradd 选项 用户名
```
参数说明：
- 选项：
  - -c comment，指定一段注释性描述。
  - -d 目录，指定用户主目录，如果此目录不存在，则同时使用-m选项，可以创建主目录。
  - -g 用户组，指定用户所属的用户组。
  - -G 用户组，指定用户所属的附加组。
  - -s Shell文件，指定用户的登录Shell。
  - -u 用户号，指定用户的用户号，如果同时有-o选项，则可以重复使用其他用户的标识号。

- 用户名：指定新账号的登录名。


例如：

```shell
$ useradd -s /bin/sh -g group -G adm,root datamonday
```

此命令新建了一个用户 datamonday，该用户的登录Shell是 `/bin/sh`，它属于group用户组，同时又属于adm和root用户组，其中group用户组是其主组。

### 5.1.2. ）`userdel` 删除用户

如果一个用户的账号不再使用，可以从系统中删除。删除用户账号就是要将 `/etc/passwd` 等系统文件中的该用户记录删除，必要时还删除用户的主目录。

删除一个已有的用户账号使用 `userdel` 命令：

```shell
$ userdel 选项 用户名
```

常用的选项是 **`-r`**，它的作用是把用户的主目录一起删除。例如：

```shell
$ userdel -r sam
```

此命令删除用户sam在系统文件中（主要是`/etc/passwd`, `/etc/shadow`, `/etc/group`等）的记录，同时删除用户的主目录。

### 5.1.3. ）`usermod` 修改账号

修改用户账号就是根据实际情况更改用户的有关属性，如用户号、主目录、用户组、登录Shell等。

修改已有用户的信息使用 `usermod` 命令：

```shell
usermod 选项 用户名
```

常用的选项包括`-c, -d, -m, -g, -G, -s, -u, -o`，这些选项的意义与`useradd`命令中的选项相同。

另外，有些系统可以使用选项 `-l` 修改新用户名，将原来的用户名改为新的用户名。例如：

```shell
$ usermod -s /bin/ksh -d /home/z –g developer sam
```

此命令将用户sam的登录Shell修改为ksh，主目录改为/home/z，用户组改为developer。

### 5.1.4. ）`passwd` 用户口令管理

用户账号刚创建时，口令被系统锁定，必须为其指定口令后才可以使用，即使是指定空口令。

超级用户可以为自己和其他用户指定口令，普通用户只能用它修改自己的口令。指定和修改用户口令的Shell命令是 `passwd`：

```shell
$ passwd 选项 用户名
```

可使用的选项：

- -l 锁定口令，即禁用账号。
- -u 口令解锁。
- -d 使账号无口令。
- -f 强迫用户下次登录时修改口令。

如果默认用户名，则修改当前用户的口令。

例如，假设当前用户是sam，则下面的命令修改该用户自己的口令：

```shell
$ passwd 
Old password:****** 
New password:******* 
Re-enter new password:*******
```

如果是超级用户，可以用下列形式指定任何用户的口令：

```shell
$ passwd sam 
New password:******* 
Re-enter new password:*******
```

为用户指定空口令时，执行下列形式的命令：

```shell
$ passwd -d sam
```

此命令将用户 sam 的口令删除，用户 sam 下一次登录时，系统就不再允许该用户登录了。

`passwd` 命令还可以用 `-l(lock)` 选项锁定某一用户，使其不能登录，例如：

```shell
$ passwd -l sam
```

------

## 5.2. 用户组的管理

每个用户都有一个用户组，系统可以对一个用户组中的所有用户进行集中管理。不同Linux 系统对用户组的规定有所不同，如Linux下的用户属于与它同名的用户组，这个用户组在创建用户时同时创建。

用户组的管理涉及用户组的添加、删除和修改。组的增加、删除和修改实际上就是对/etc/group文件的更新。

### 5.2.1. ）`groupadd` 增加新用户组

```shell
groupadd 选项 用户组
```

可用选项：

- -g GID，指定新用户组的组标识号（GID）。
- -o 一般与-g选项同时使用，表示新用户组的GID可以与系统已有用户组的GID相同。

例1：

```shell
$ groupadd group1
```

此命令向系统中增加了一个新组group1，新组的组标识号是在当前已有的最大组标识号的基础上加1。

例2：

```shell
$ groupadd -g 101 group2
```

此命令向系统中增加了一个新组group2，同时指定新组的组标识号是101。

### 5.2.2. ）`groupdel` 删除已有用户组

```shell
groupdel 用户组
```

例1：

```shell
$ groupdel group1
```

此命令从系统中删除组group1。

### 5.2.3. ）`groupmod` 修改用户组属性

```shell
groupmod 选项 用户组
```

常用选项：

- -g GID，为用户组指定新的组标识号。
- -o 与-g选项同时使用，用户组的新GID可以与系统已有用户组的GID相同。
- -n 新用户组，将用户组的名字改为新名字。

例1：

```shell
$ groupmod -g 102 group2
```

此命令将组group2的组标识号修改为102。

例2：

```shell
$ groupmod –g 10000 -n group3 group2
```

此命令将组group2的标识号改为10000，组名修改为group3。

### 5.2.4. ）`newgrp` 切换用户组

如果一个用户同时属于多个用户组，则用户可以在用户组之间切换，以便具有其他用户组的权限。

用户可以在登录后，使用命令 `newgrp` 切换到其他用户组，这个命令的参数就是目的用户组。例如：

```shell
$ newgrp root
```

这条命令将当前用户切换到root用户组，前提条件是root用户组确实是该用户的主组或附加组。

------

## 5.3. 与用户账号有关的系统文件

用户管理实际上都是对有关的系统文件进行修改。与用户和用户组相关的信息都存放在一些系统文件中，包括/etc/passwd, /etc/shadow, /etc/group等。

### 5.3.1. ）`/etc/passwd` 

Linux系统中的每个用户都在/etc/passwd文件中有一个对应的记录行，它记录了这个用户的一些基本属性。

这个文件对所有用户都是可读的：

```shell
$ cat /etc/passwd

root:x:0:0:Superuser:/:
daemon:x:1:1:System daemons:/etc:
bin:x:2:2:Owner of system commands:/bin:
sys:x:3:3:Owner of system files:/usr/sys:
adm:x:4:4:System accounting:/usr/adm:
uucp:x:5:5:UUCP administrator:/usr/lib/uucp:
auth:x:7:21:Authentication administrator:/tcb/files/auth:
cron:x:9:16:Cron daemon:/usr/spool/cron:
listen:x:37:4:Network daemon:/usr/net/nls:
lp:x:71:18:Printer administrator:/usr/spool/lp:
sam:x:200:50:Sam san:/home/sam:/bin/sh
```

**`/etc/passwd` 中一行记录对应一个用户**，每行记录被冒号(:)分隔为7个字段，其具体含义如下：

```shell
用户名:口令:用户标识号:组标识号:注释性描述:主目录:登录Shell
```

- 1）**用户名**：代表用户账号的字符串。通常长度不超过8个字符，由大小写字母和/或数字组成。登录名中不能有冒号(:)，因为冒号在这里是分隔符。为了兼容起见，登录名中最好不要包含点字符(.)，并且不使用连字符(-)和加号(+)开头。

- 2）**口令**：存放着加密后的用户口令字。虽然这个字段存放的只是用户口令的加密串，不是明文，但是由于/etc/passwd文件对所有用户都可读，所以这仍是一个安全隐患。因此，现在**许多Linux 系统（如SVR4）都使用了shadow技术，把真正的加密后的用户口令字存放到 `/etc/shadow` 文件中，而在 `/etc/passwd` 文件的口令字段中只存放一个特殊的字符，例如 x 或者 * **。

- 3）**用户标识号**：整数，用来标识用户。它与用户名一一对应。如果几个用户名对应的用户标识号是一样的，系统内部将把它们视为同一个用户，但是它们可以有不同的口令、不同的主目录以及不同的登录Shell等。

  通常用户标识号的取值范围是0～65 535。**0是超级用户root的标识号，1～99由系统保留，作为管理账号，普通用户的标识号从100开始**。在Linux系统中，这个界限是500。

- 4）**组标识号**：记录用户所属的用户组。它对应着/etc/group文件中的一条记录。

- 5）**注释性描述**：记录用户的个人情况。

  例如用户的真实姓名、电话、地址等，这个字段并没有什么实际的用途。在不同的Linux 系统中，这个字段的格式并没有统一。在许多Linux系统中，这个字段存放的是一段任意的注释性描述文字，用做finger命令的输出。

- 6）**主目录**：用户的起始工作目录，即用户在登录到系统之后所处的目录。在大多数系统中，各用户的主目录都被组织在同一个特定的目录下，而**用户主目录的名称就是该用户的登录名**。各用户对自己的主目录有读、写、执行（搜索）权限，其他用户对此目录的访问权限则根据具体情况设置。

- 7）**Shell**：用户登录后，要启动一个**进程，负责将用户的操作传给内核，这个进程是用户登录到系统后运行的命令解释器或某个特定的程序，即Shell**。

  **Shell是用户与Linux系统之间的接口**。Linux的Shell有许多种，每种都有不同的特点。常用的有sh(Bourne Shell), bash(Bourne Again Shell)等。

  系统管理员可以指定Shell。如果不指定，则系统默认的登录Shell为sh，即这个字段的值为 `/bin/sh`。

  用户的登录Shell也可以指定为某个特定的程序（此程序不是一个命令解释器）。

- 8）**伪用户（pseudo users）**：这些用户在 `/etc/passwd` 文件中也占有一条记录，但是不能登录，因为它们的登录Shell为空。作用是方便系统管理，满足相应的系统进程对文件属主的要求。

  常见的伪用户如下所示：

  ```shell
  bin 拥有可执行的用户命令文件 
  sys 拥有系统文件 
  adm 拥有帐户文件 
  uucp UUCP使用 
  lp lp或lpd子系统使用 
  nobody NFS使用
  ```

  除了上面列出的伪用户外，还有许多标准的伪用户，例如：audit, cron, mail, usenet等，它们也都各自为相关的进程和文件所需要。

  由于/etc/passwd文件是所有用户都可读的，很容易被破解。**对安全性要求较高的Linux系统都把加密后的口令字分离出来，单独存放在一个文件中，这个文件是 `/etc/shadow` 文件**。有超级用户才拥有该文件读权限，这就保证了用户密码的安全性。

---

### 5.3.2. ）`/etc/shadow`

`/etc/shadow` 中的记录行与 `/etc/passwd` 中的一一对应，它由 `pwconv` 命令根据 `/etc/passwd` 中的数据自动产生。它的文件格式与 `/etc/passwd` 类似，由若干个字段组成，字段之间用 `:` 隔开。字段为：

```shell
登录名:加密口令:最后一次修改时间:最小时间间隔:最大时间间隔:警告时间:不活动时间:失效时间:标志
```
- 1）**登录名**：与 `/etc/passwd` 文件中的登录名相一致的用户账号。
- 2）**加密口令**：存放加密后的用户口令字，长度为13个字符。如果为空，则对应用户没有口令，登录时不需要口令；如果含有不属于集合 { ./0-9A-Za-z } 中的字符，则对应的用户不能登录。
- 3）**最后一次修改时间**：表示的是从某个时刻起，到用户最后一次修改口令时的天数。时间起点对不同的系统可能不一样。SCO Linux 中的时间起点是1970年1月1日。
- 4）**最小时间间隔**：两次修改口令之间所需的最小天数。
- 5）**最大时间间隔**：口令保持有效的最大天数。
- 6）**警告时间**：从系统开始警告用户到用户密码正式失效之间的天数。
- 7）**不活动时间**：用户没有登录活动但账号仍能保持有效的最大天数。
- 8）**失效时间**：一个绝对的天数，如果使用了这个字段，则给出相应账号的生存期。期满后，该账号不再合法，也就不能再登录。

/etc/shadow例子：

```shell
$ cat /etc/shadow

root:Dnakfw28zf38w:8764:0:168:7:::
daemon:*::0:0::::
bin:*::0:0::::
sys:*::0:0::::
adm:*::0:0::::
uucp:*::0:0::::
nuucp:*::0:0::::
auth:*::0:0::::
cron:*::0:0::::
listen:*::0:0::::
lp:*::0:0::::
sam:EkdiSECLWPdSa:9740:0:0::::
```

### 5.3.3. ）`/etc/group` 

将用户分组是Linux 系统中对用户进行管理及控制访问权限的一种手段。**用户组的所有信息都存放在 `/etc/group` 文件中**。每个用户都属于某个用户组；一个组中可以有多个用户，一个用户也可以属于不同的组。

当一个用户同时是多个组中的成员时，在 `/etc/group` 文件中记录的是用户所属的主组，即登录时所属的默认组，而其他组称为附加组。用户要访问属于附加组的文件时，必须首先使用 `newgrp` 命令使自己成为所要访问的组中的成员。用户组的所有信息都存放在 `/etc/group`  文件中。此文件的格式也类似于 `/etc/passwd` 文件，由冒号 `:` 隔开若干个字段：

```shell
组名:口令:组标识号:组内用户列表
```
- 1）**组名**：用户组名称，由字母或数字构成。与/etc/passwd中的登录名一样，组名不应重复。
- 2）**口令**：用户组加密后的口令字。一般Linux 系统的用户组都没有口令，即这个字段一般为空，或者是*。
- 3）**组标识号**：与用户标识号类似，也是一个整数，被系统内部用来标识组。
- 4）**组内用户列表**：是属于这个组的所有用户的列表/b]，不同用户之间用逗号 `,` 分隔。这个用户组可能是用户的主组，也可能是附加组。

/etc/group文件的例子：

```shell
root::0:root
bin::2:root,bin
sys::3:root,uucp
adm::4:root,adm
daemon::5:root,daemon
lp::7:root,lp
users::20:root,sam
```

### 5.3.4. ）添加批量用户

Linux系统提供了创建大量用户的工具。

1. **先编辑一个文本用户文件。**

   每一列按照`/etc/passwd`密码文件的格式书写，要注意每个用户的用户名、UID、宿主目录都不可以相同，其中密码栏可以留做空白或输入x号。一个范例文件 `user.txt` 内容如下：

   ```shell
   user001::600:100:user:/home/user001:/bin/bash
   user002::601:100:user:/home/user002:/bin/bash
   user003::602:100:user:/home/user003:/bin/bash
   user004::603:100:user:/home/user004:/bin/bash
   user005::604:100:user:/home/user005:/bin/bash
   user006::605:100:user:/home/user006:/bin/bash
   ```

2. **以root身份执行命令 `/usr/sbin/newusers`，从刚创建的用户文件`user.txt`中导入数据，创建用户**：

   ```shell
   $ newusers < user.txt
   ```

   然后可以执行命令 `vipw` 或 `vi /etc/passwd`，检查 `/etc/passwd` 文件是否已经出现这些用户的数据，并且用户的宿主目录是否已经创建。

3. **执行命令 `/usr/sbin/pwunconv`**。

   将 `/etc/shadow` 产生的 `shadow` 密码解码，然后回写到 `/etc/passwd` 中，为方便下一步的密码转换，删除 `/etc/shadow` 的 `shadow` 密码栏，即先取消 `shadow password` 功能。

   ```shell
   $ pwunconv
   ```

4. **编辑每个用户的密码对照文件**。

   格式为：

   ```shell
   $ username:password
   ```

   实例文件 `passwd.txt` 内容如下：

   ```shell
   user001:123456
   user002:123456
   user003:123456
   user004:123456
   user005:123456
   user006:123456
   ```
   
5.  **以 root 身份执行命令 `/usr/sbin/chpasswd`**。

   创建用户密码，`chpasswd` 会将经过 `/usr/bin/passwd` 命令编码过的密码写入 `/etc/passwd` 的密码栏。

   ```shell
$ chpasswd < passwd.txt
   ```

6. **确定密码经编码写入 `/etc/passwd` 的密码栏**。
   
   执行命令 `/usr/sbin/pwconv` 将密码编码为 `shadow password`，并将结果写入 `/etc/shadow`。
   
   ```shell
   $ pwconv
   ```
   
   至此完成大量用户创建，在 `/home` 下可以检查这些用户宿主目录的权限设置是否都正确，并登录验证用户密码是否正确。

---

# 6. 磁盘管理

Linux磁盘管理好坏直接关系到整个系统的性能问题。Linux磁盘管理常用三个命令为df、du和fdisk。

- `df`：列出文件系统的整体磁盘使用量。
- `du`：检查磁盘空间使用量。
- `fdisk`：用于磁盘分区。

## 6.1. df 检查文件系统的磁盘使用

检查文件系统的磁盘空间占用情况。语法：

```shell
$ df [-ahikHTm] [目录或文件名]
```

选项与参数：

- -a ：列出所有的文件系统，包括系统特有的 /proc 等文件系统；
- -k ：以 KBytes 的容量显示各文件系统；
- -m ：以 MBytes 的容量显示各文件系统；
- -h ：以易读的 GBytes, MBytes, KBytes 等格式显示；
- -H ：以 M=1000K 取代 M=1024K 的进位方式；
- -T ：显示文件系统类型，连同该 partition 的 filesystem 名称 (例如 ext3) 也列出；
- -i ：不用硬盘容量，而以 inode 的数量来显示

以易读的容量格式显示出来：

![image-20210422214752470](./imgs/image-20210422214752470.png)

将系统内的所有特殊文件格式及名称都列出来：

![image-20210422214922310](./imgs/image-20210422214922310.png)

---
## 6.2 du 检查文件和目录磁盘使用

查看文件和目录磁盘的使用空间。语法：

```shell
$ du [-ahskm] 文件或目录名称
```

选项与参数：

- -a ：列出所有的文件与目录容量，因为默认仅统计目录底下的文件量而已。
- -h ：以人们较易读的容量格式 (G/M) 显示；
- -s ：列出总量而已，而不列出每个各别的目录占用容量；
- -S ：不包括子目录下的总计，与 -s 有点差别。
- -k ：以 KBytes 列出容量显示；
- -m ：以 MBytes 列出容量显示；

检查根目录底下每个目录所占用的容量

```shell
$ du -sm /*
```


---

## 6.3 fdisk 磁盘分区表

fdisk 是 Linux 的磁盘分区表操作工具。语法：

```shell
$ fdisk [-l] 装置名称
```

选项与参数：

- `-l `：输出后面接的装置所有的分区内容。若仅有 fdisk -l 时， 则系统将会把整个系统内能够搜寻到的装置的分区均列出来。

列出所有分区信息

```shell
$ fdisk -l
```

---
## 6.4 mkfs 磁盘格式化

磁盘分割完毕后自然就是要进行文件系统的格式化，格式化的命令非常的简单，使用 `mkfs`（make filesystem） 命令。

语法：

```shell
$ mkfs [-t 文件系统格式] 装置文件名
```

选项与参数：

- -t ：可以接文件系统格式，例如 ext3, ext2, vfat 等，系统有支持才会生效。

---
## 6.5 fsck 磁盘检验

`fsck`（file system check）用来检查和维护不一致的文件系统。

若系统掉电或磁盘发生问题，可利用fsck命令对文件系统进行检查。

语法：

```shell
$ fsck [-t 文件系统] [-ACay] 装置名称
```

选项与参数：

- -t : 给定档案系统的型式，若在 /etc/fstab 中已有定义或 kernel 本身已支援的则不需加上此参数
- -s : 依序一个一个地执行 fsck 的指令来检查
- -A : 对/etc/fstab 中所有列出来的 分区（partition）做检查
- -C : 显示完整的检查进度
- -d : 打印出 e2fsck 的 debug 结果
- -p : 同时有 -A 条件时，同时有多个 fsck 的检查一起执行
- -R : 同时有 -A 条件时，省略 / 不检查
- -V : 详细显示模式
- -a : 如果检查有错则自动修复
- -r : 如果检查有错则由使用者回答是否修复
- -y : 选项指定检测每个文件是自动输入yes，在不确定那些是不正常的时候，可以执行 # fsck -y 全部检查修复。

查看系统有多少文件系统支持的 fsck 命令：

![image-20210422215231026](./imgs/image-20210422215231026.png)

强制检测 /dev/hdc6 分区:

```shell
$ fsck -C -f -t ext3 /dev/hdc6 
```

## 6.6 mount 磁盘挂载与卸载

Linux 的磁盘挂载使用 `mount` 命令，卸载使用 `umount` 命令。

磁盘挂载语法：

```shell
$ mount [-t 文件系统] [-L Label名] [-o 额外选项] [-n]  装置文件名  挂载点
```


用默认的方式，将刚刚创建的 /dev/hdc6 挂载到 /mnt/hdc6 上面！

```shell
$ mkdir /mnt/hdc6
$ mount /dev/hdc6 /mnt/hdc6
$ df
Filesystem           1K-blocks      Used Available Use% Mounted on
.....中间省略.....
/dev/hdc6              1976312     42072   1833836   3% /mnt/hdc6
```

磁盘卸载命令 `umount` 语法：

```shell
$ umount [-fn] 装置文件名或挂载点
```

选项与参数：

- -f ：强制卸除！可用在类似网络文件系统 (NFS) 无法读取到的情况下；
- -n ：不升级 /etc/mtab 情况下卸除。

卸载/dev/hdc6

```shell
$ umount /dev/hdc6     
```

---

> Ref:
>
> 1. [Linux 教程](https://www.runoob.com/linux/linux-system-contents.html)
> 2. [Linux命令大全](https://www.runoob.com/linux/linux-command-manual.html)

