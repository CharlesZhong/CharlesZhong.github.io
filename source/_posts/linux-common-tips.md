---
title: linux_common_tips
date: 2016-01-07 03:22:58
<<<<<<< HEAD
tags: Linux
=======
tags: Linux, Shell, 
>>>>>>> a889e061beb040a8c1ffa23ca7269ce972276d65
---

#1 mkdir
```
> mkdir -p a/b/c
```

#2 cd
shell 自带命令

```
> cd -  # 返回目录
```

#3 ln

##3.1 硬连接

* 不能跨分区
* 不能对目录
* 相同的 inode 节点，增加引用计数

##3.2 软链接 -s

* 相当于快捷方式  
* 不增加引用计数
* block 存 inode
* 777
* 软连接要写绝对路径

#4 locate

> updatedb

/etc/updatedb.conf


#5 whereis

查询系统命令

#6 whichis

命令所在位置
还会显示令别名


#8 find

```
> find / -name test.txt 完全匹配
> find / -name “test.log*”

? * []

find /root -iname install.log 不去’大小写
find /root -user root 
find /root -nouser // 内核数据，外来文件 没有所有者，其他的可能是垃圾文件

find /root -mtime +10 十天前修改的文件 -10 十天前 10 十天当天
-atime 访问时间

find . -size 25K
find . -i 2000

find /etc -size +20K -a size -50K
-o or -a and

find /etc -size +20K -a size -50K -exec ls -lh {} \;
```

#9 grep

```
grep “man” test.txt

grep -v “man” test.txt
```

#10 man

```
man -k passwd 相关命令
man -f passwd 命令及
```

#11 .zip

```
zip to.zip from.zip
zip -r dir.zip ori_dir
unzip ori.zip
```

#12 .gz

```
gzip file      源文件消失
gzip -C file  > file.gz 不消失

gzip -r dir 把目录下文件压缩 不压缩目录

gunzip -d abc.gz
gunzip -r abc
```

#13 .bz2

```
bzip2 file
bzip2 -k file > file.bz2
不压缩目录
```

#14 .tar.gz
打包

```
tar -cvf  -c 打包 -v 显示过程 -f 指定打包后文件名
tar -cvf test.tar ori_file

tar -x 解打包

-z gz -j bz2

tar -zcvf  直接压缩成 tar.gz
tar -zxvf 解压缩
tar -ztvf 查看不解压缩
```

#15 shutdown

```
-h 关机
-r 重启

> shutdown -r 5:30 &

> runlevel 查看系统级别 0-6 /etc/inittab 设置 
```

#16 挂载

```
> mount 查看挂载好的
> mount -a  自动挂载 /etc/fstab
> mout [-t 文件系统] ext4 [-o 特殊选项] 设备名 挂载点

out -o remote, no exec /home
```

#17 挂载U盘

```
> fdisk -l 
ntfs-3g 可读但不可写
```

#18 w 查看用户登录信息

```
> w
> who
```

#19 last 
登录信息 保存 /var/log/wtmp

#20 lastlog
所有永用户的登录信息

#21 echo  颜色输出
```
> echo -e “\e[1;31m xxx \e[0m”
```
