#  宝塔安装swoole 4.4.23版本(宝塔版本)

## 下载

首先进入 `Swoole` 的 `Github` 下载地址: https://github.com/swoole/swoole-src/releases

如果没有特殊需求，请选择最新稳定版本开始下载(我这里是稳定版v4.4.23):

````shell
## 下载
wget https://github.com/swoole/swoole-src/archive/v4.4.23.tar.gz
## 解压到当前目录
tar -zvxf v4.4.23.tar.gz

## cd 到解压之后的目录
cd swoole-src-4.4.23/ 

## 使用 phpize 创建 php 编译检测脚本 ./configure
##【注意：需要选择 php 对应版本的 phpize，这里使用的是绝对路径，否则编译安装无法生效】
##/usr/local/php-7.2.2/bin/phpize

/www/server/php/74/bin/phpize


## 创建编译文件，第一个 --with，后面是 php-config 的所在路径(这个路径一般和 php 在同一个目录) /usr/local/php-7.2.2/bin/php-config，第二个 --enable，是开启 Swoole 的 ssl 功能，第三个 --enable(可选参数)，是开启 Swoole 支持 http2 相关的功能
 ./configure --with-php-config=/www/server/php/74/bin/php-config --enable-openssl --enable-http2

## 编译 Swoole 并把编译好的文件移动到 php 的扩展目录(前面的配置 php 版本的扩展目录) 需要root权限
 sudo make && make install 

## 编译成功会显示如下：
Build complete.
Don't forget to run 'make test'.

Installing shared extensions:     /usr/local/php-7.2.2/lib/php/extensions/no-debug-non-zts-20160303/
Installing header files:          /usr/local/php-7.2.2/include/php/

````

