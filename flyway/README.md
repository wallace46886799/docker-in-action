# 操作步骤
0、构建本地镜像
docker build -t flyway_myproj:v1 .

1、创建本地挂接目录
创建SQL文件目录
mkdir -p ${pwd}/flyway/sql
创建配置文件目录
mkdir -p ${pwd}/flyway/conf
创建驱动文件目录
mkdir -p ${pwd}/flyway/drivers

2、运行docker容器
docker run --name flyway_myproj --rm -v ${pwd}/flyway/sql:/flyway/sql -v ${pwd}/flyway/conf:/flyway/conf -v ${pwd}/flyway/drivers:/flyway/drivers flyway_myproj:v1


# 参考
https://hub.docker.com/r/boxfuse/flyway/
