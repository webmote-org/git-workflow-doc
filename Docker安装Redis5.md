# Docker下安装Redis 5
1. [参考文档Redis的配置](https://redis.io/topics/config)
2. [参考文档Redis下载](https://redis.io/download)
3. [参考文档Redis的Docker镜像](https://hub.docker.com/_/redis/)

安装完Docker，使用下列命令拉取最新的Redis 
```
docker pull redis
```
# 映射Redis配置步骤（坑）
**请一定按照顺序进行，否则，你会查看到Redis.conf是文件夹**
1. 选择配置保存的目录，这里为 /data/conf/redis.conf
```
# 建立文件
cd /data/conf
touch redis.conf
# 编辑redis.conf,内容如下：
bind 0.0.0.0
requirepass 123.com
protected-mode no
```
2. 建立redis容器
```
docker run -d -p 6379:6379 -v /data/conf/redis.conf:/usr/local/etc/redis/redis.conf --name myredis redis redis-server /usr/local/etc/redis/redis.conf
```
客户机使用 telnet 判断是否建立OK
一切顺利的话，搞定。
