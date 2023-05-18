#基于哪个镜像
FROM tomcat:8.0

#镜像创建者
MAINTAINER Frank "46886799@163.com"

#用来设置环境变量,KV结构
ENV TOMCAT_MAJOR 8
ENV TOMCAT_VERSION 8.0.42

#安装软件用
RUN mkdir -p /usr/local/tomcat/webapps/myproj
#Tomcat的安装目录为/usr/local/tomcat
COPY conf/context.xml /usr/local/tomcat/conf
COPY conf/server.xml /usr/local/tomcat/conf
#安装软件用



#container内部服务开启的端口。主机上要用还得在启动container时，做host-container的端口映射：
EXPOSE 8080 8443


#Container启动时执行的命令，但是一个Dockerfile中只能有一条CMD命令，多条则只执行最后一条CMD.
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]
