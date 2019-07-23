# linux常用命令

1、压缩文件命令
```
	tar -cvf Project_yaochiwan.tar .[!.]* *
```

2、解压文件命令
```
	tar -xvf yaochiwan.tar
```

3、项目迁移到另一台服务器
```
首先进入到新服务器，然后执行下面命令

对拷命令:
rsync -az --progress --exclude-from=/www/exclude.list root@139.196.169.192:/web/nideshop/ /web/nideshop/
```

4、压缩数据库

```
	mysqldump -u root -p nideshop>nideshop.sql
```

5、删除文件
```
	rm -f /lanmp_v3.1.tar.gz
```

6、链接数据库
```
	mysql -h localhost -u root -p Q0YoiopfEGPC7rF9XbJ
```