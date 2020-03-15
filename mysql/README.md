# 操作步骤
0、构建本地镜像
docker build -t mysql_myproj:v1 .

1、创建本地挂接目录
mkdir -p ${pwd}/mysql/data
mkdir -p ${pwd}/mysql/conf

2、运行docker容器
docker run --name mysql_myproj -p 3306:3306 -v ${pwd}/mysql/data:/var/lib/mysql -v ${pwd}/mysql/conf:/etc/mysql/conf.d  -e MYSQL_ROOT_PASSWORD=123456 -d  mysql_myproj:v1

#docker run --name mysql_myproj -p 3306:3306 -v /Users/Frank/Work/Docker/mysql/data:/var/lib/mysql -v /Users/Frank/Work/Docker/mysql/conf:/etc/mysql/conf.d  -e MYSQL_ROOT_PASSWORD=123456 -d  mysql_myproj:v1

# 导出数据
## 1、备份命令
格式：mysqldump -h主机名 -P端口 -u用户名 -p密码 --database 数据库名 > 文件名.sql
例如： mysqldump -h 192.168.1.100 -p 3306 -uroot -ppassword --database cmdb > /data/backup/cmdb.sql

## 2、备份压缩
导出的数据有可能比较大，不好备份到远程，这时候就需要进行压缩
格式：mysqldump -h主机名 -P端口 -u用户名 -p密码 --database 数据库名 | gzip > 文件名.sql.gz
例如： mysqldump -h192.168.1.100 -p 3306 -uroot -ppassword --database cmdb | gzip > /data/backup/cmdb.sql.gz

## 3、备份同个库多个表
格式：mysqldump -h主机名 -P端口 -u用户名 -p密码 --database 数据库名 表1 表2 .... > 文件名.sql
例如 mysqldump -h192.168.1.100 -p3306 -uroot -ppassword cmdb t1 t2 > /data/backup/cmdb_t1_t2.sql

## 4、同时备份多个库
格式：mysqldump -h主机名 -P端口 -u用户名 -p密码 --databases 数据库名1 数据库名2 数据库名3 > 文件名.sql
例如：mysqldump -h192.168.1.100 -uroot -ppassword --databases cmdb bbs blog > /data/backup/mutil_db.sql

## 5、备份实例上所有的数据库
格式：mysqldump -h主机名 -P端口 -u用户名 -p密码 --all-databases > 文件名.sql
例如：mysqldump -h192.168.1.100 -p3306 -uroot -ppassword --all-databases > /data/backup/all_db.sql

## 6、备份数据出带删除数据库或者表的sql备份
格式：mysqldump -h主机名 -P端口 -u用户名 -p密码 --add-drop-table --add-drop-database 数据库名 > 文件名.sql
例如：mysqldump -uroot -ppassword --add-drop-table --add-drop-database cmdb > /data/backup/all_db.sql

## 7、备份数据库结构，不备份数据
格式：mysqldump -h主机名 -P端口 -u用户名 -p密码 --no-data 数据库名1 数据库名2 数据库名3 > 文件名.sql
例如：mysqldump --no-data –databases db1 db2 cmdb > /data/backup/structure.sql


# 导入数据库
## 1、首先建空数据库
mysql>create database abc;

## 2、导入数据库
### 方法一：
（1）选择数据库
mysql>use abc;
（2）设置数据库编码
mysql>set names utf8;
（3）导入数据（注意sql文件的路径）
mysql>source /home/abc/abc.sql;
### 方法二：
mysql -u用户名 -p密码 数据库名 < 数据库名.sql
#mysql -uabc_f -p abc < abc.sql
