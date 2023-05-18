#基于哪个镜像
FROM webcenter/activemq:5.14.3

#镜像创建者
MAINTAINER Frank "46886799@163.com"

#用来设置环境变量,KV结构
#docker run --name='activemq' -d \
#-e 'ACTIVEMQ_CONFIG_NAME=amqp-srv1' \
#-e 'ACTIVEMQ_CONFIG_DEFAULTACCOUNT=false' \
#-e 'ACTIVEMQ_ADMIN_LOGIN=admin' -e 'ACTIVEMQ_ADMIN_PASSWORD=your_password' \
#-e 'ACTIVEMQ_USERS_myproducer=producerpassword' -e 'ACTIVEMQ_GROUPS_writes=myproducer' \
#-e 'ACTIVEMQ_USERS_myconsumer=consumerpassword' -e 'ACTIVEMQ_GROUPS_reads=myconsumer' \
#-e 'ACTIVEMQ_JMX_user1_role=readwrite' -e 'ACTIVEMQ_JMX_user1_password=jmx_password' \
#-e 'ACTIVEMQ_JMX_user2_role=read' -e 'ACTIVEMQ_JMX_user2_password=jmx2_password'
#-e 'ACTIVEMQ_CONFIG_TOPICS_topic1=mytopic1' -e 'ACTIVEMQ_CONFIG_TOPICS_topic2=mytopic2'  \
#-e 'ACTIVEMQ_CONFIG_QUEUES_queue1=myqueue1' -e 'ACTIVEMQ_CONFIG_QUEUES_queue2=myqueue2'  \
#-e 'ACTIVEMQ_CONFIG_MINMEMORY=1024' -e  'ACTIVEMQ_CONFIG_MAXMEMORY=4096' \
#-e 'ACTIVEMQ_CONFIG_SCHEDULERENABLED=true' \
#-v /data/activemq:/data \
#-v /var/log/activemq:/var/log/activemq \
#-p 8161:8161 \
#-p 61616:61616 \
#-p 61613:61613 \
#webcenter/activemq:5.14.3

ENV ACTIVEMQ_CONFIG_NAME amqp-srv1
ENV ACTIVEMQ_CONFIG_DEFAULTACCOUNT false
ENV ACTIVEMQ_ADMIN_LOGIN admin
ENV ACTIVEMQ_ADMIN_PASSWORD admin
ENV ACTIVEMQ_USERS_myproducer producerpassword
ENV ACTIVEMQ_GROUPS_writes myproducer
ENV ACTIVEMQ_USERS_myconsumer consumerpassword
ENV ACTIVEMQ_GROUPS_reads myconsumer
ENV ACTIVEMQ_JMX_user1_role readwrite
ENV ACTIVEMQ_JMX_user1_password jmx_password
ENV ACTIVEMQ_JMX_user2_role read
ENV ACTIVEMQ_JMX_user2_password jmx2_password
ENV ACTIVEMQ_CONFIG_TOPICS_topic1 mytopic1
ENV ACTIVEMQ_CONFIG_TOPICS_topic2 mytopic2
ENV ACTIVEMQ_CONFIG_QUEUES_queue1 myqueue1
ENV ACTIVEMQ_CONFIG_QUEUES_queue2 myqueue2
ENV ACTIVEMQ_CONFIG_MINMEMORY 1024
ENV ACTIVEMQ_CONFIG_MAXMEMORY 4096
ENV ACTIVEMQ_CONFIG_SCHEDULERENABLED true

#安装软件用

#安装软件用



#container内部服务开启的端口。主机上要用还得在启动container时，做host-container的端口映射：
EXPOSE 8161 8161
EXPOSE 61616 61616
EXPOSE 61613 61613


#Container启动时执行的命令，但是一个Dockerfile中只能有一条CMD命令，多条则只执行最后一条CMD.
#docker run --name='activemq' -it --rm -P webcenter/activemq:latest
