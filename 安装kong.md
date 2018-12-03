## 1、下载指定的对应的RPM文件
https://bintray.com/kong/kong-community-edition-rpm/centos

## 2、通过yum命令进行安装
1）sudo yum install epel-release

2）sudo yum install kong-community-edition-0.14.1.*.noarch.rpm --nogpgcheck
3）kong version

## 3、通过Docker安装PostgreSQL数据库
1）创建数据库数据存储目录：mkdir -p ~/postgres/data 

2）拉取对应版本号的数据库镜像：docker pull postgres:9.5

3）启动对应的镜像：docker run --name csfrezpostgres -v $PWD/data:/var/lib/postgresql/data -e POSTGRES_USER=kong -e POSTGRES_PASSWORD=kong@123 -p 5432:5432 -d postgres:9.5

## 4、初始化Kong网关数据库并启动
1）配置kong.conf，对应的目录/etc/kong

2）配置模板链接： kong.conf

3）初始化：  kong migrations up 

4）启动Kong：kong start

## 5、通过Docker安装pgbi/kong-dashboard(管理端)
1）镜像目录：https://hub.docker.com/r/pgbi/kong-dashboard/

2）拉取镜像：docker pull pgbi/kong-dashboard

3）启动镜像：docker run --name csfrezkongdashboard -itd -p 8080:8080 pgbi/kong-dashboard start --kong-url http://127.0.0.1:8001
