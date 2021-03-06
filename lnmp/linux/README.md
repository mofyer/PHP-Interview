# Linux部分

## 目录

* [操作系统概述](https://github.com/xianyunyh/PHP-Interview/tree/master/Linux#操作系统概述)
* [Linux历史](https://github.com/xianyunyh/PHP-Interview/tree/master/Linux#gnu和gpl)
* [Linux基本命令](https://github.com/xianyunyh/PHP-Interview/blob/master/Linux/Linux命令.md)
* [Linux\(磁盘网络相关命令\)](https://github.com/xianyunyh/PHP-Interview/blob/master/Linux/Linux命令2.md)
* [Crontab计划任务](https://github.com/xianyunyh/PHP-Interview/blob/master/Linux/crontab.md)
* [shell](https://github.com/xianyunyh/PHP-Interview/blob/master/Linux/shell.md)
* [进程和线程](https://github.com/xianyunyh/PHP-Interview/blob/master/Linux/shell.md)
* [AWK命令](https://github.com/xianyunyh/PHP-Interview/blob/master/Linux/AWK练习.md)
* [SED命令](https://github.com/xianyunyh/PHP-Interview/blob/master/Linux/Sed练习.md)

## 操作系统概述

操作系统，英文名称Operating System，简称OS，是计算机系统中必不可少的基础系统软件，它是应用程序运行以及用户操作必备的基础环境支撑，是计算机系统的核心。

​ 操作系统的作用是管理和控制计算机系统中的硬件和软件资源，例如，它负责直接管理计算机系统的各种硬件资源，如对CPU、内存、磁盘等的管理，同时对系统资源所需的优先次序进行管理。操作系统还可以控制设备的输入、输出以及操作网络与管理文件系统等事务。同时，它也负责对计算机系统中各类软件资源的管理。例如各类应用软件的安装、设置运行环境等。操作系统与计算机硬件软件关系图如下。

![img](https://images2015.cnblogs.com/blog/1066162/201611/1066162-20161130112310443-1027054412.png)

## Linux和Ｕnix

Unix系统于1969年在AT&T的贝尔实验室诞生，20世纪70年代，它逐步盛行，这期间，又产生了一个比较重要的分支，就是大约1977年诞生的BSD（Berkeley Software Distribution）系统。从BSD系统开始，各大厂商及商业公司开始了根据自身公司的硬件架构，并以BSD系统为基础进行Unix系统的研发，从而产生了各种版本的Unix系统.

70年代中后期，由于各厂商和商业公司开发的Unix及内置软件都是针对自己公司特定的硬件，因此在其他公司的硬件上基本无法直接运行，而且当时没有人对开发基于x86架构的CPU的系统感兴趣。另外，70年代末，Unix又面临了突如其来的被AT&T回收版权的重大问题，特别是要求禁止对学生群体提供Unix系统源代码，这样的问题一度引起了当时Unix业界的恐慌，也因此产生了商业纠纷。

Linux系统的诞生开始于1991年芬兰赫尔辛基大学的一位计算机系的学生，名字为**Linus Torvalds**。在大学期间，他接触到了学校的Unix系统，但是当时的Unix系统仅为一台主机，且对应了多个终端，使用时存在操作等待时间很长等一些不爽的问题，无法满足年轻的Linus Torvalds的使用需求。因此他就萌生了自己开发一个Unix的想法，于是不久，他就找到了前文提到的谭邦宁教授开发的用于教学的Minix操作系统，他把Minix安装到了他的I386个人计算机上。此后，Torvalds又开始陆续阅读了Minix系统的源代码，从Minix系统中学到了很多重要的系统核心程序设计理念和设计思想，从而逐步开始了Linux系统雏形的设计和开发。

## GNU和GPL

GNU的全称为**GNU's not unix**，意思是"GNU不是UNIX"，GNU计划，又称革奴计划，是由Richard Stallman在1984年公开发起的，是FSF的主要项目。这个项目的目标是建立一套完全自由的和可移植的类Unix操作系统。

​ GNU类Unix操作系统是由一系列应用程序、系统库和开发工具构成的软件集合，例如：Emacs编辑软件、gcc编译软件、bash命令解释程序和编程语言，以及gawk（GNU's awk）等，并加上了用于资源分配和硬件管理的内核。

​ 到1991年Linux内核发布的时候，GNU项目已经完成了除系统内核之外的各种必备软件的开发。在Linux Torvalds和其他开发人员的努力下，GNU项目的部分组件又运行到了Linux内核之上，例如：GNU项目里的Emacs、gcc、bash、gawk等，至今都是Linux系统中很重要的基础软件。所以linux 又叫**GNU/Linux**

GPL全称为General Public License，中文名为通用公共许可，是一个最著名的开源许可协议，开源社区最著名的Linux内核就是在GPL许可下发布的。GPL许可是由自由软件基金会（Free Software foundation）创建的。

