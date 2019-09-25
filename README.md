# onlyoffice-in-docker
使用docker-compose编排解决onlyoffice的部署


https://www.linuxbabe.com/docker/onlyoffice-nextcloud-integration-docker


## 如何使用

* 在项目的certs目录中放置https证书文件：key跟crt文件，cer不需要，并重命名为onlyoffice.crt和onlyoffice.key

* 检测系统docker跟docker-compose的环境是否正常

	````
		docker -v
		docker-compose -v
	````

	关于如何下载docker以及docker-compose可以参考这篇文章：https://www.linuxbabe.com/docker/onlyoffice-nextcloud-integration-docker

* 修改docker-compose.yml的配置，搜索hostname，并将值改为自己的站点域名
	
* 启动项目：

	````
		docker-compose up -d
	````

* 停止项目：

	````
		docker-compose down
	````

* 查看项目日志

	在community/log下查看	onlyoffice-community-server的系统运行日志

	在document/log下查看onlyoffice-document-server的系统运行日志

	在mail/log下查看邮箱日志

	如果要直接查看docker内的系统启动日志

	通过命令 docker ps 查看有哪些服务在运行

	再通过命令 docker logs -t -f --tail 100 ${server_name} 进行查看

* 数据库相关

	* 数据库默认密码为：my-secret-pw，要修改请编辑docker-compose.yml文件，修改MYSQL_ROOT_PASSWORD的值，并修改MAIL_SERVER_DB_PASS和MYSQL_SERVER_PASS、MYSQL_SERVER_DB_NAME的值

	* 数据库数据存放目录为 ./mysql_data	







