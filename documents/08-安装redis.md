# Ubuntu安装Redis
使用`apt`可以实现快速安装Redis。
```shell
sudo apt install redis
```

安装完毕后，后台会自动运行Redis服务。可以使用`systemctl`查看服务状态。
```shell
sudo systemctl status redis
```
设置Redis服务的开机启动。
```shell
sudo systemctl enable redis-server
```

## 配置

通过上述方式安装的Redis配置文件为`/etc/redis/redis.conf`，数据存放路径为`/var/lib/redis`，默认无访问权限，需要修改权限。
```shell
sudo chmod 777 /etc/redis
sudo chmod 777 /var/lib/redis
```
随后即可根据需要修改配置文件，我的修改如下：
```
# 密码
requirepass 123456
# 数据存放路径
dir /var/lib/redis
```

修改完毕后，需要重启Redis服务。
```shell
sudo systemctl restart redis
```

## 简单使用
打开终端
```shell
# 开启Redis Client
redis-cli

# 输入密码
auth 123456

#查看是否有响应
ping  #PONG

# 新建一个键值对
set name "张三"
# 查看键值对
get name
# 查看所有键
keys *
# 清屏
clear

```

