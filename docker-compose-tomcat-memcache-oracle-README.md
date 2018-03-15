# docker-in-action
docker-compose-tomcat-memcache-oracle.yml完成了一键启动tomcat、memcached、oracle<br/>
###运行命令
docker-compose -f docker-compose-tomcat-memcache-oracle.yml up  -d
<br>
其中：docker-compose-tomcat-memcache-oracle.yml 也可以带上绝对路径
###文件说明
context：是指路径的上下文，在build的过程中都会以这个目录为基准，寻找dockerfile,最好直接写绝对路径<br>
${my_proj}：本地目录, 用于目录映射 <br>
容器内访问，可以直接通过<b>container_name</b>定义的值进行访问：例如：jdbc的数据库访问连接串可以如下：<br>
jdbc:oracle:thin:@db-oracle:1521:orcl
<br>
访问memcached：11211<br>
无需具体指定具体的ip地址
