#Mysql Image

### Creating and using custom mysql data shared folder

```
docker run --name mysql-container -v /var/www/databases/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:latest
```
