# 操作步骤
0、构建本地镜像
docker build -t redis_myproj:v1 .



2、运行docker容器
docker run -p 11211:11211 --name redis_myproj:v1 -d memcached

例如：docker run -p 11211:11211 --name my-memcache -d memcached


