# Redis优化

## 1.tcp-backlog ,默认为511

1. #### 说明:此参数确定了TCP连接中已完成队列(完成三次握手之后)的长度， 当然此值必须不大于Linux系统定义的/proc/sys/net/core/somaxconn值，默认是511，而Linux的默认参数值是128。当系统并发量大并且客户端速度缓慢的时候，可以将这二个参数一起参考设定。

2. 建议修改为  2048

   ```shell
   ##修改somaxconn
   ##该内核参数默认值一般是128，对于负载很大的服务程序来说大大的不够。一般会将它修改为2048或者更大。
   ##但是这样系统重启后保存不了
   echo 2048 > /proc/sys/net/core/somaxconn 
   ## 在/etc/sysctl.conf中添加如下  net.core.somaxconn = 2048
   sysctl -p
   ```

   

#### 















