# linux安装wdcp


1、下载
```
进入Linux，直接下载（不用进入任何文件夹内）

	wget http://dl.wdlinux.cn/lanmp_laster.tar.gz

	注：
	wget：是Linux的命令表示从网络下载内容
	tar：解压命令
```

2、解压
```
	tar zxvf lanmp_laster.tar.gz
```

3、安装
```
	sh lanmp.sh
	
	
	如果
	报错：lanmp.sh: 45: lib/common.conf: function: not found
　　					lanmp.sh: 67: lib/common.conf: Syntax error: "}" unexpected
	解决方法：
	先执行：sudo dpkg-reconfigure dash
	选择no
	再执行：sudo sh lanmp.sh即可安装
```

4、选择要安装的内容：选择4安装全部

5、卸载wdcp
```
	sh lanmp.sh un
```
