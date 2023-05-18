# 操作步骤
0、构建本地镜像
docker build -t redis_myproj:v1 .

1、创建本地挂接目录
mkdir -p ${pwd}/data


2、运行docker容器
docker run --name redis_myproj  -p 6379:6379 -v ${pwd}/data:/data -d redis_myproj:v1
例如：docker run --name redis_myproj  -p 6379:6379 -v /Users/Frank/Work/Frameworks/GitHub/docker-in-action/redis/data:/data -d redis_myproj:v1


3、Redis Cluster：https://github.com/Grokzen/docker-redis-cluster


