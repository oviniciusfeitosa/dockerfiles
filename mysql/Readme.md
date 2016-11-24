#Mysql Image

### Create container 

Let's create container using: 
- custom mysql data shared folder;
- custom mysql configuration folder; 
- custom mysql log folder;
```
docker run --name mysql-container  -v /private/var/www/databases/mysql/conf.d:/etc/mysql/conf.d -v /private/var/www/databases/mysql/data:/var/lib/mysql  -v /private/var/www/databases/mysql/log:/var/log/ -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_ROOT_HOST=0.0.0.0 -d mysql:latest
```

### Accessing docker container
```
docker exec -it mysql-container bash
```

* The MySQL Server log is located at /var/log/mysqld.log inside the container, and the following command line from a shell inside the container will let you inspect it:

```
more /var/log/mysqld.log
```
