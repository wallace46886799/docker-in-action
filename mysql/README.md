# 操作步骤
0、构建本地镜像
docker build -t mysql_myproj:v1 .

1、创建本地挂接目录
mkdir -p ${pwd}/mysql/data
mkdir -p ${pwd}/mysql/conf

2、运行docker容器
docker run --name mysql_myproj -p 3306:3306 -v ${pwd}/mysql/data:/var/lib/mysql -v ${pwd}/mysql/conf:/etc/mysql/conf.d  -e MYSQL_ROOT_PASSWORD=123456 -d  mysql_myproj:v1

#docker run --name mysql_myproj -p 3306:3306 -v /Users/Frank/Work/Docker/mysql/data:/var/lib/mysql -v /Users/Frank/Work/Docker/mysql/conf:/etc/mysql/conf.d  -e MYSQL_ROOT_PASSWORD=123456 -d  mysql_myproj:v1
