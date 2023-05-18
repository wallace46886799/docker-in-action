# 操作步骤
0、构建本地镜像
docker build -t zookeeper_myproj:v1 .

1、运行docker容器
docker run --name zookeeper_myproj --privileged=true -ti -p 2181:2181 -d zookeeper_myproj:v1


