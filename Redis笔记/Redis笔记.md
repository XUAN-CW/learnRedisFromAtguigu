# 安装

## 下载

## 安装

### 材料

- CentOS 7.3
- redis-3.0.4.tar.gz

### 安装与启动

```shell
cd /opt #下载获得redis-3.0.4.tar.gz后将它放入我们的Linux目录/opt
tar -zxvf redis-3.0.4.tar.gz # 解压
# 进入并安装
cd redis-3.0.4
make
make install
vim redis.conf # 在这里要把 daemonize no 改成 daemonize yes ,让服务在后台启动
cd /usr/local/bin/
redis-server /opt/redis-3.0.4/redis.conf # 启动服务
```

#### 修改 `redis.conf` 

这里是对上面 `vim redis.conf` 这一命令的说明。编辑 `redis.conf`，把 `daemonize no` 改成 `daemonize yes`，如下所示：

```shell
################################ GENERAL  #####################################

# By default Redis does not run as a daemon. Use 'yes' if you need it.
# Note that Redis will write a pid file in /var/run/redis.pid when daemonized.
daemonize yes
```

#### 没有 gcc

```
[root@10 redis-3.0.4]# yum install gcc-c++
```

### 测试

```shell
[root@iztggh9oymm8slz bin]# redis-cli -p 6379
127.0.0.1:6379> ping
PONG
127.0.0.1:6379> set k1 hello
OK
127.0.0.1:6379> get k1
"hello"
127.0.0.1:6379> 
```

### 进入与停止

```shell
# 进入
redis-cli -p 6379
```

```shell
# 停止
127.0.0.1:6379> SHUTDOWN
not connected> exit
```

## [安装全过程](./log/redis.log)

