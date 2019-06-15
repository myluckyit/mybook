# git的常用命令

## 一、创建项目

### 方法一

直接在码云或者GitHub平台创建项目即可，然后通过git把改项目拉取到本地

```
git clone https://github.com/myluckyit/test.git

表示将GitHub上的test项目拉取到本地
```

## 方法二，直接通过git来创建新项目

1. 在本地创建一个空文件夹test2

2. 进入到该文件夹，打开git窗口执行以下命令
```
git init	

这样通过git init命令就可以把这个目录变成Git可以管理的仓库
``` 


## 二、查看

查看即将提交的内容

```
git diff --cached

或 

git status

```


