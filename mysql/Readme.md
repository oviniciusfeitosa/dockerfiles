#Mysql Image

### About

  For this scenario we will use the "mysql" image and "latest" tag.

### Create container 

  Let's create container using: 
  - custom mysql data shared folder;
  - custom mysql configuration folder; 
  - custom mysql log folder;
  - custom root password : 123456
  - custom user : admin
  - custom user password : admin
  - custom mysql root Host : 0.0.0.0
```
docker run --name mysql-container  -v /private/var/www/databases/mysql/conf.d:/etc/mysql/conf.d -v /private/var/www/databases/mysql/data:/var/lib/mysql  -v /private/var/www/databases/mysql/log:/var/log/ -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_ROOT_HOST=0.0.0.0 -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin -p 3306:3306 -e right="WRITE" -d mysql:latest
```
  Or, without configuration folder: 
  - custom mysql data shared folder;
  - custom mysql log folder;
  - custom root password : 123456
  - custom user : admin
  - custom user password : admin
  - custom mysql root Host : 0.0.0.0
```
docker run --name mysql-container -v /private/var/www/databases/mysql/data:/var/lib/mysql  -v /private/var/www/databases/mysql/log:/var/log/ -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin  -e MYSQL_ROOT_HOST=0.0.0.0  -e right="WRITE" -d mysql:latest
```
   Or, maybe MOREEE simple:
  - custom mysql log folder;
  - custom root password : 123456
  - custom user : admin
  - custom user password : admin
  - custom mysql root Host : 0.0.0.0
```
docker run --name mysql-container -v /private/var/www/databases/mysql/log:/var/log/ -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_ROOT_HOST=0.0.0.0 -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin -p 3306:3306 -e right="WRITE" -d mysql:latest
```

   EVEN MORE simple! So...
  - custom mysql log folder;
  - custom root password : 123456
  - custom mysql root Host : 0.0.0.0
```
docker run --name mysql-container -v /private/var/www/databases/mysql/log:/var/log/ -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_ROOT_HOST=0.0.0.0 -p 3306:3306 -e right="WRITE" -d mysql:latest
```

### Accessing docker container
```
docker exec -it mysql-container bash
```

* The MySQL Server log is located at /var/log/mysqld.log inside the container, and the following command line from a shell inside the container will let you inspect it:

```
more /var/log/mysqld.log
```
