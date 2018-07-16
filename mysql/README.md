#### Volume structure

- /var/lib/mysql: Database files
- /var/lib/mysql/mysql-bin: MariaDB logs

#### Environment Variables:

#### Main Mariadb parameters:

- MYSQL_DATABASE: specify the name of the database
- MYSQL_USER: specify the User for the database
- MYSQL_PASSWORD: specify the User password for the database
- MYSQL_ROOT_PASSWORD: specify the root password for Mariadb

https://mariadb.org/

#### Creating an instance
```shell
docker run -it --name mysql -p 3306:3306 
-v /var/lib/mysql:/var/lib/mysql 
-e MYSQL_DATABASE=wordpressdb 
-e MYSQL_USER=wordpressuser 
-e MYSQL_PASSWORD=hguyFt6S95dgfR4ryb 
-e MYSQL_ROOT_PASSWORD=hguyFtgfR4r9R4r76 
yobasystems/alpine-mariadb
```

```yml
mysql:
  image: yobasystems/alpine-mariadb
  environment:
    MYSQL_ROOT_PASSWORD: hguyFtgfR4r9R4r76
    MYSQL_DATABASE: wordpressdb
    MYSQL_USER: wordpressuser
    MYSQL_PASSWORD: hguyFt6S95dgfR4ryb
  expose:
    - "3306"
  volumes:
    - /data/example/mysql:/var/lib/mysql
  restart: always
```

[The article comes from](https://github.com/yobasystems/alpine-mariadb/blob/master/alpine-mariadb-amd64/files/run.sh)