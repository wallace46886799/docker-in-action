# 操作步骤
0、构建本地镜像
docker build -t memcached_myproj:v1 .

1、运行docker容器
docker run -p 11211:11211 --name memcached_myproj -d memcached_myproj:v1
