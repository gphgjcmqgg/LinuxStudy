# linux挂载

## mount命令的基本格式

linux所有设备都必须挂载使用，包括硬盘

mount             
查看系统已经挂载的设备


## 挂载光盘

光盘的设备文件名是/dev/sr0

设备文件名和已经建立好的空目录联系起来

mount -t iso9660 /dev/cdrom /mnt/cdrom       --挂载光盘
umount /mnt/cdrom                            --卸载光盘

## 挂载U盘

U盘会和硬盘共用设备文件名，所以U盘的设备文件名不是固定，需要手动查询
fdisk -l      --查询硬盘

mount -t vfat /dev/sdb1 /mnt/usb                              --挂载U盘
mount -t vfat -o iocharset=utf8 /dev/sdb4 /mnt/usb            --挂载U盘支持中文

## 自动挂载

mount -a                  --检测自动挂载文件配置
依据配置文件/etc/fstab的内容，自动挂载

## 挂载ntfs分区

驱动后缀.ko
驱动保存在/lib/modules/3.10.0-862.el7.x86_64/kernel/中
