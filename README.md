# docker-in-action
## 已完善的Docker file：tomcat、oracle、redis、mysql、zookeeper
## 待完善的Docker file：jenkins、sonar、nexus

# Mac下安装Docker运行环境
https://docs.docker.com/docker-for-mac/install/

# Mac下安装Docker Compose
https://docs.docker.com/compose/install/

# 目标
使用docker-compose快速启动所有运行环境，包括面向基于Mysql和Oracle数据库的两类应用。

## 近期计划
1、完善memcache的Dockerfile  <b>已完成</b>  <br>
2、完成docker-compose.yml的编写，保证启动后tomcat可以访问memcache（redis）和oracle（mysql）<br>
3、研究flyway解决sql导入方案
