#### 常见Linux命令

##### 1、chmod

更改文件属性

linux文件的基本权限有9个，分别是owner/group/others三种身份各有自己的read/write/execute权限

各权限的分数对照表如下： r:4   w:2   x:1

##### 2、ls

列出目录

##### 3、cd

切换目录

##### 4、pwd

显示当前目录

##### 5、mkdir

创建文件夹

##### 6、rmdir

删除空的文件夹

##### 7、cp

拷贝文件夹或文件

```shell
cp 来源档 目标档
```

##### 8、rm

删除文件或文件夹

##### 9、mv

移动文件夹或文件

```shell
mv 来源档 目标档
```

##### 10、cat

文件查看

##### 11、more

文件查看，一页一页查看

##### 12、touch

创建一个文件

##### 13、软连接与硬连接

硬连接通过索引节点来进行连接，多个文件名指向同一索引节点，但是两个文件名指向同一文件，对文件系统来说是完全平等的，删除其中任何一个都不会影响另外一个的访问， 以防止“误删”

软连接类似于Windows的快捷方式，是“主从”关系

硬连接

```shell
ln f1 f2
```

软连接

```python
ln -s f1 f2
```

##### 14、shutdown

linux关机

##### 15、reboot

linux重启

##### 16、du

查看文件或文件夹的使用空间

##### 17、echo

字符串输出

```shell
>>> echo "hello"
hello
```

##### 18、 find

用来找指定目录下查找文件

```shell
find path  -name ".*c" #查找当前目录中后缀为'.c'的文件列出来
```

##### 19、which

用来查找文件，会在环境变量$PATH设置的目录里查找符合条件的文件

##### 20、scp

远程传输

从本地复制到远程

```shell
scp [-r] local_file remote_username@remote_ip:remote_folder
```

从远程复制到本地

```
scp [-r] remote_username@remote_id:remote_floder local_file
```

##### 21、grep

用来查找内容包含指定的范本样式的文件，如果发现某文件的内容符合所指定的范本样式，预设grep指定会把范本样式的那一列显示出来

```shell
grep test *file  #在当前目录中，查找后缀有file字样的文件中包含test字符串的文件，并打印出该字符串的行
```

##### 22、tree

用于以树状图列出目录的内容

##### 23、ping

检测是否与主机联通

##### 24、ps

用于显示当前进程的状态，类似于windows的任务管理器

##### 25、top

用于实时显示process的动态

##### 26、export

显示环境变量



linux中>表示覆盖原文件内容（文件的日期也会自动更新），>>表示追加内容（会另起一行，文件的日期也会自动更新）