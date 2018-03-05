#Parent image
FROM mysql:latest

#镜像创建者
MAINTAINER Frank "46886799@163.com"

#用来设置环境变量,KV结构

#安装软件用
RUN apt-get update
RUN apt-get -y install vim
RUN usermod -u 1000 mysql
RUN mkdir -p /var/run/mysqld
RUN chmod -R 777 /var/run/mysqld

#container内部服务开启的端口。主机上要用还得在启动container时，做host-container的端口映射：
EXPOSE 3306


#Container启动时执行的命令，但是一个Dockerfile中只能有一条CMD命令，多条则只执行最后一条CMD.
