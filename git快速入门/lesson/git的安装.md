# git的安装

## 一、在Windows上安装Git
在Windows上使用Git，可以从Git官网直接下载安装程序，（网速慢的同学请移步国内镜像），然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

## 二、安装完成后，还需要最后一步设置，在命令行输入：

```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。
这个名字是你注册的gitee(码云)/GitHub等代码托管平台的账号时用的邮箱和设置的名字。

*注意：如果设置不成功，可以多执行几次这个两行命令。*