# LinuxStudy

## 虚拟机网络

| 连接方式    | 连接网卡    |  是否能连接本机  | 能否能连接局域网 | 是否能连接公网
| --------   | -----:     | :----:         |:----:           |:----:       |
| 桥接       | 本地真实网卡 |  可以           |       可以        |       可以        |
| NAT        |   VMnet8    |   可以           |       不能        |       可以        |
| 仅主机     |    VMnet1    |   可以           |       不能        |       不能        |
