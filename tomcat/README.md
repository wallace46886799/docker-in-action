# 操作步骤
0、修改server.xml和context.xml
修改server.xml关于端口的定义；增加context.xml中关于数据源的定义


1、构建本地镜像
docker build -t tomcat_myproj:v1 .

2、创建本地挂接目录
mkdir  ${pwd}/myproj


3、拷贝应用到${pwd}/myproj


4、运行docker容器
docker run --name tomcat_myproj --privileged=true -ti  -p 8080:8080 -d -v ${pwd}/myproj:/usr/local/tomcat/webapps/myproj tomcat_myproj:v1

docker run --name tomcat_myproj_v2 --privileged=true -ti  -p 8080:8080 -d -v /Users/Frank/Work/Frameworks/GitHub/docker-in-action/tomcat/myproj:/usr/local/tomcat/webapps/myproj tomcat_myproj:v2
