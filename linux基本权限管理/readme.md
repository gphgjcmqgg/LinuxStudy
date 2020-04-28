# 基本权限管理

文件权限的查看：
-rw-r--r-- 1 root root 216 may 12 2017 /mnt/rht
第一位代表:文件类型
-普通文件
d 目录
l 软链接
s 套接字
c 字符设备（显示字符，如date命令）/dev/pts/1 date > /dev/pts/1

第2到第10位：文件的权限
rw-|r--|r--
u   g   o
u: user(所有者)
g: group(组)
o: other

r 读权限read        4
w 写权限write       2
x 操作权限execute   1

## 基本权限命令

### chmod     修改权限的命令

英文愿意：change file mode bits
chmod [选项] 权限模式 文件名
选项：
  -R：递归设置权限，也就是给子目录中的所有文件设定权限

例子：
chmod u+w,g+w,o+w bcd
chmod u-w,g-w,o-w bcd
chmod u=rwx bcd
chmod 755 bcd

## 所有者和所属组命令

useradd user1
passwd  user1

### chown       是修改文件和目录的所有者和所属组的命令

英文原意：change file owner and group
chown [选项] 所有者:所属组 文件或目录

chown user1 文件名
chown root:root 文件名

普通用户不能修改文件的所有者，哪怕自己是这个文件的所有者也不行
普通用户可以修改所有者是自己的文件的权限

### chgrp命令

chgrp是修改文件和目录的所属组的命令
