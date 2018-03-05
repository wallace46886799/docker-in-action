0、创建本地挂接目录
mkdir  ${pwd}/myproj

1、构建本地镜像
docker build -t tomcat_myproj:v1 .

2、拷贝应用到${pwd}/tomcat/webapps/myproj

3、运行docker容器
docker run -ti -v ${pwd}/myproj:/usr/local/tomcat/webapps/myproj tomcat_myproj:v1


