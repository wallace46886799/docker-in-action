# 操作步骤
0、修改server.xml和context.xml
修改server.xml关于端口的定义；增加context.xml中关于数据源的定义


1、构建本地镜像
修改Dockerfile的“RUN mkdir -p /usr/local/tomcat/webapps/myproj”，将myproj修改为应用的上下文，例如demo；
执行docker build -t tomcat_myproj:v1 .

2、创建本地挂接目录
mkdir  ${pwd}/myproj，与上述的demo目录对应。


3、拷贝应用到${pwd}/myproj，与上述的demo目录对应。


4、运行docker容器
docker run --name tomcat_myproj --privileged=true -ti  -p 8080:8080 -d -v ${pwd}/myproj:/usr/local/tomcat/webapps/myproj tomcat_myproj:v1
