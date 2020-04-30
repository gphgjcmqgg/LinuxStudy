# linux关机重启

1. sync数据同步

刷新文件系统缓冲区

2. shutdown

shutdown [option] 时间 [警告信息]
option:
  -c:       取消已经执行的shtudown
  -h:       关机
  -r:       重启
shutdown -r now
shutdown -r 05:30

3. reboot         重启

4. halt和poweroff  不建议使用

5. init 0         关机
6. init 6         重启