#基于哪个镜像
FROM nginx:1.9

#镜像创建者
MAINTAINER Frank "46886799@163.com"

#用来设置环境变量,KV结构


#安装软件用
RUN rm /etc/nginx/conf.d/default.conf

ADD nginx.conf /etc/nginx/conf.d/


#container内部服务开启的端口。主机上要用还得在启动container时，做host-container的端口映射：
EXPOSE 80 443


#Container启动时执行的命令，但是一个Dockerfile中只能有一条CMD命令，多条则只执行最后一条CMD.




