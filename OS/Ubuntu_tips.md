# 【整理】Ubuntu 学习笔记

Ubuntu 也短短续续用了不短时间，虚拟机的常驻系统之一，但是上周末在家里远程部署一个 Flask 小项目时竟然把一些命令又忘了，，为了改善这种现用现忘现查的情况，也为了以后查询更方便😁，特此整理。

## apt 安装包时提示找不到

这很可能是因为你首次使用 apt，还没有对其更新造成的。通过以下命令更新即可：

```shell
apt update
```

> 注意，很多包都需要 root 权限，注意切换用户。


## snap "*" has "install-snap" change in progress
通过 snap store 同时安装多个应用，尤其是在前一个尚未安装完，就安装下一个的时候，往往会出现此错误提示。这是因为安装进程仍在进行中，至少是它认为仍在进行中。

怎么解决呢？在万能的终端中输入如下命令，查看正在进行的安装：

```shell
$ snap changes

ID Status  Spawn                Ready       Summary
1  Doing   today at 11:09 CST   -           Install "AppName" snap
```

应该能在结果中看到，你想装而装不了的应用，状态为 `Doing`。这就是问题的所在了，接下我来我们只要在终端中终止它就可以了。

```shell
sudo snap abort 1
```

注意命令中 `abort` 的是 id，要与上一条命令的结果中的条目 id 相同。

> 如果你跟我一样，对 Snap 不甚了解，那么可以参见这篇文章：[《Ubuntu 18.04及Snap体验》](https://www.linuxidc.com/Linux/2018-06/152993.htm)
