# jiacrontab
提供可视化界面的定时任务管理工具。

1.允许设置每个脚本的超时时间，超时操作可选择邮件通知管理者，或强杀脚本进程。  
2.允许设置脚本的最大并发数。  
3.一台server管理多个client。  
4.每个脚本都可在server端灵活配置，如测试脚本运行，查看日志，强杀进程，停止定时...。  
5.允许添加脚本依赖（支持跨服务器），依赖脚本提供同步和异步的执行模式。  
6.友好的web界面，方便用户操作。  
7.脚本出错时可选择邮箱通知多人。  


## 说明
jiacrontab由server，client两部分构成，两者完全独立通过rpc通信。  
server：向用户提供可视化界面，调度多个client。  
client：实现定时逻辑，隔离用户脚本，将client布置于多台服务器上可由server统一管理。
每个脚本的定时格式完全兼容linux本身的crontab脚本配置格式。

## 安装
#### 二进制安装  
1.[下载](http://git.wzjg520.com/wzjg520/jiacrontab/releases) 二进制文件。  

2.解压缩进入目录。  

3.运行  
```sh
$ nohup ./server &> server.log &
$ nohup ./client &> client.log &     
```
### 源码安装
1.安装git，golang；可参考官网。  
2.安装运行
```sh
$ cd $GOPATH/src
$ git clone http://git.wzjg520.com:/wzjg520/jiacrontab.git 
$ go get -u github.com/dgrijalva/jwt-go
$ go get -u gopkg.in/ini.v1

$ cd $GOPATH/src/jiacrontab/server
$ go build .
$ nohup ./server &> server.log &

$ cd $GOPATH/src/jiacrontab/client
$ go build .
$ nohup ./client &> client.log & 
``` 

### 版本升级

1、下载新版本压缩包，并解压。  

2、替换旧版本中的server(或server.exe)、client(或client.exe)执行文件，以及static、template目录为新版


## 截图
![alt 截图](https://raw.githubusercontent.com/iwannay/static_dir/master/jiacrontab_preview_1.jpg)  

![alt 截图2](https://raw.githubusercontent.com/iwannay/static_dir/master/jiacrontab_preview_2.jpg)

## 演示地址
[demo](http://jiacrontab.wzjg520.com) 账号：admin 密码：123456

## qq群成立啦
813377930 欢迎反馈问题
