# 操作步骤
PS.请先阅读：https://dev.aliyun.com/detail.html?spm=5176.1972343.2.2.2f075aaaBU6Ush&repoId=1969

0、构建本地镜像 <br>
docker build -t oracle_11g_myproj:v1 .

1、创建本地挂接目录 <br>
mkdir -p ${pwd}/oracle/data <br>
mkdir -p ${pwd}/oracle/flash_recovery_area/helowin <br>
#mkdir -p /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/data <br>
#mkdir -p /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/flash_recovery_area/helowin <br>

2、运行docker容器
docker run -d --name oracle_11g_myproj -p 1521:1521 oracle_11g_myproj:v1 -v ${pwd}/oracle/data:/home/oracle/app/oracle/oradata -v ${pwd}/oracle/flash_recovery_area/helowin:/home/oracle/app/oracle/flash_recovery_area/helowin


#docker run -d --name oracle_11g_myproj -p 1521:1521 oracle_11g_myproj:v1 -v /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/data:/home/oracle/app/oracle/oradata -v /Users/Frank/Work/Frameworks/GitHub/docker-in-action/oracle/flash_recovery_area/helowin:/home/oracle/app/oracle/flash_recovery_area/helowin



# 创建用户
1.进入容器 docker exec -it 容器ID /bin/bash

2.加载环境变量 source /home/oracle/.bash_profile

3.登录 sqlplus /nolog

connect /as sysdba 到这里就可以进行您想要的任何操作了

容器系统用户 root：helowin

（如需用plsql工具连接 请设置用户和密码） 举例：

create user test identified by test;

grant connect,resource,dba to test;




# 常见问题
## 解决 ORA-21561: OID generation failed
http://blog.csdn.net/elonlink/article/details/52635523
