#### docker设置镜像源

[docker 设置国内镜像源](https://blog.csdn.net/whatday/article/details/86770609)

创建或修改 `etc/docker/daemon.json`，修改为如下形式：

```json
# vi /etc/docker/daemon.json
{
    "registry-mirrors": ["http://hub-mirror.c.163.com"]
}
```

重启docker服务：`systemctl restart docker.service`





#### docker安装redis

[安装redis](https://www.runoob.com/docker/docker-install-redis.html)

获取最新版镜像：`docker pull redis:latest`

查看本地镜像：`docker images`

运行容器：`docker run -itd --name redis-test -p 6379:6379 redis`，其中`-p 6379:6379`表示映射容器服务的6379端口到宿主机的6379端口；

安装成功：`docker ps` 查看容器运行