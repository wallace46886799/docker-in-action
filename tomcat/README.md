0、构建本地镜像
docker build -t tomcat_myproj:v1 .

1、创建本地挂接目录
mkdir  ${pwd}/myproj


2、拷贝应用到${pwd}/myproj


3、运行docker容器
docker run --name tomcat_myproj --privileged=true -ti  -p 8080:8080 -d -v ${pwd}/myproj:/usr/local/tomcat/webapps/myproj tomcat_myproj:v1


