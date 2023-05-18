# docker-in-action
## 脚本说明
docker-compose-tomcat-redis-mysql.yml完成了一键启动tomcat、redis、mysql
## 运行命令
docker-compose -f docker-compose-tomcat-redis-mysql.yml up  -d
<br>
其中：docker-compose-tomcat-redis-mysql.yml 也可以带上绝对路径
## 文件说明
context：是指路径的上下文，在build的过程中都会以这个目录为基准，寻找dockerfile<br>
${my_proj}：本地目录, 用于目录映射 <br>
容器内访问，可以直接通过<b>container_name</b>定义的值进行访问：例如：jdbc的数据库访问连接串可以如下：<br>
jdbc:mysql://db:3306/i2fdb <br>
访问redis：redis:6379<br>
无需具体指定具体的ip地址
