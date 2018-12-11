# CentOS安装Docker，需要先卸载旧的Docker版本，然后安装 CE版Docker
** 坑：旧版本Docker不支持 From as 命令，然后 Dotnet Core建立的dockerfile不能执行 ** 
安装步骤请参考Docker 官方安装文档：

1. [Docker安装文档](https://docs.docker.com/install/linux/docker-ce/centos/#install-docker-ce-1)
2. [DockerFile文档说明](https://docs.docker.com/engine/reference/builder/)

# .net core 程序运行在docker
1. git拉取代码
2. 生成docker镜像
 ```docker build -t shykes/myapp .```
3. 运行镜像
```
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```
4. 运行容器
```
docker start xxx #容器id 前4位即可
```
