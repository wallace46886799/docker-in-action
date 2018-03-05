PS.请先阅读：https://dev.aliyun.com/detail.html?spm=5176.1972343.2.2.2f075aaaBU6Ush&repoId=1969

0、构建本地镜像
docker build -t oracle_11g_myproj:v1 .

1、创建本地挂接目录
mkdir -p ${pwd}/oracle/data
mkdir -p ${pwd}/oracle/flash_recovery_area/helowin
#mkdir -p /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/data
#mkdir -p /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/flash_recovery_area/helowin

2、运行docker容器
docker run -d --name oracle_11g_myproj -p 1521:1521 oracle_11g_myproj:v1 -v ${pwd}/oracle/data:/home/oracle/app/oracle/oradata -v ${pwd}/oracle/flash_recovery_area/helowin:/home/oracle/app/oracle/flash_recovery_area/helowin


#docker run -d --name oracle_11g_myproj -p 1521:1521 oracle_11g_myproj:v1 -v /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/data:/home/oracle/app/oracle/oradata -v /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/flash_recovery_area/helowin:/home/oracle/app/oracle/flash_recovery_area/helowin