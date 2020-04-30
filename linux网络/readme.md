# linux网络

## 配置IP地址

IP地址是计算机在互联网中唯一的地址编码。每台计算机如果需要接入网络和其他计算机进行数据通信，就必须配置唯一的公网IP地址

配置IP地址有两种方法：
1. setup工具
2. vi /etc/sysconfig/network-scripts/ifcfg-eth0

## 重启网络服务

service network restart

## UUID冲突问题         

复制镜像有可能需要重置UUID（唯一识别码）

解决方案：
1. vi /etc/sysconfig/network-scripts/ifcfg-eth0
删除MAC地址行

2. rm -rf /etc/udev/rules.d/70-persistent-net.rules
删除MAC地址和UUID绑定文件

3. 重启linux  shutdown -r now

## ifconfig

查询网卡和ip地址信息

## ping命令

通过ICMP协议进行网络探测，测试网络中主机的通信情况

## netstat

netstat是网络状态查看命令，既可以查看到本机开启的端口，也可以查看有哪些客户端连接。
在centos7.x中netstat默认没有安装，需要安装net-snmp和net-tools软件包

netstat [options]

options:
1. -a       列出所有网络状态，包括Socket程序
2. -p	      显示正在使用Socket的程序识别码PID和程序名称
3. -u	      显示UDP传输协议的连线状况
4. -t	      显示TCP传输协议的连线状况
5. -i       显示网络界面信息表单
6. -n	      直接使用IP地址，不通过域名服务器
7. -l       仅显示监听状态的连接
8. -r       显示路由表

查看本机开启的端口
netstat -tuln

查看本机有哪些程序开启的端口
netstat -tulnp

查看所有连接
netstat -an

查看默认网关
netstat -rn

## 登录终端

  本地字符终端            tty1-6          alt+F1-6

## 系统痕迹命令

### w命令

显示系统中正在登录的用户

### who命令

显示系统中正在登录的用户，但是显示的内容更加简单

### last命令

查看系统所有登陆过的用户信息，包括正在登录的用户和之前登录的用户

### lastlog命令

查看系统所有用户最后一次的登录时间的命令

### lastb命令

查看错误登录的信息