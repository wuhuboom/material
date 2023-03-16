# 安装Goland  1.18.4

````shell
## 首先我们到Golang 官网（由于国内无法访问 Golang 官网，推荐到Golang 中文网下载安装包）下载一个对应操作系统的安装包。
cd /tmp && wget https://studygolang.com/dl/golang/go1.18.4.linux-amd64.tar.gz
## 解压缩安装包：
tar -zxvf go1.18.4.linux-amd64.tar.gz -C /opt
## 在 /etc/profile 文件末尾添加以下内容，将 Golang 可执行文件目录添加到系统 PATH 中，之后
vim /etc/profile
在文件末尾添加 export PATH=$PATH:/opt/go/bin
## 使用source生效配置。
source /etc/profile
## 配置环境变量#
go env -w GOPROXY=https://goproxy.cn,direct
go env -w GO111MODULE=on
````

