###  文档地址

http://www.ityouknow.com/docker/2018/03/07/docker-introduction.html



###  补充命令

```
docker run  --name container_name image 运行镜像，生产容器名为container_name的容器 

docker rm ae1243541123 删除容齐
docker rmi ae1243541123 删除镜像（在镜像存在容器的时候无法删除镜像，需要删除容器）
docker ps 查看运行中的容器
docker ps -a 查看所有的容器


docker start container_name/container_id 启动容器
docker stop container_name/container_id 停止容器
docker restart container_name/container_id 重启容器
docker exec -it rabbit /bin/bash 进入容器
docker rm $(docker ps -a -q) 删除所有停止的容器


```

