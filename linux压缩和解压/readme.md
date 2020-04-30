# linux压缩和解压

## linux常用压缩格式

.zip、.gz、.bz2、.tar、.tar.gz、.tar.bz2、

### zip

1. zip [option] 压缩包名 源文件或源目录
option：
  -r：    压缩目录
zip test.zip abc abcd

2. unzip [option] 压缩包名

option:
  -d:     指定解压位置
upzip -d /tmp/ test.zip

### gzip    不会打包

1. gzip [option] 源文件
2. gzip -d 压缩包名

### tar       打包不压缩

tar [option] [-f 压缩包] 源文件或目录
option:
  -c:     打包
  -f:     指定压缩包的名
  -v:     显示打包文件过程
  -t      测试，就是不解压包，只是查看包中有哪些文件
tar -cvf ana.tar ana

  -x:     解压包
tar -xvf ana.tar

### .tar.gz和.tar.bz2

使用tar命令直接打包压缩
tar [option] 压缩包 源文件或目录
option：
  -z:         压缩和解压.tar.gz格式
  -j:         压缩和解压.tar.bz2格式

  -c:         打包
  -x:         解压包

  -f:         指定压缩包的名

  -v:         显示打包文件过程
  -t          测试，就是不解压包，只是查看包中有哪些文件
  -C          解压到指定位置，选项跟在压缩包后面

tar -zcvf tmp.tar.gz /tmp/                --压缩
tar -zxvf tmp.tar.gz                      --解压
tar -ztvf tmp.tar.gz                      --只查看不解压
tar -zxvf tmp.tar.gz -C /tmp/             --解压到指定位置
tar -zxvf tmp.tar.gz -C /tmp/  123/hjk    --解压压缩包内指定文件到指定位置