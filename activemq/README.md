# 操作步骤
1、构建本地镜像
执行docker build -t activemq\_myproj:v1 .

2、创建本地挂接目录
mkdir -p ${pwd}/data/activemq，与容器中的/data目录对应。
mkdir -p ${pwd}/log/activemq，与容器中的/var/log/activemq目录对应。

3、运行docker容器
docker run --name activemq\_myproj -ti -d -v ${pwd}/data/activemq:/data -v ${pwd}/log/activemq:/var/log/activemq activemq\_myproj:v1

