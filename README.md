# docker-compose for LNMR

## Intro
docker-compose
* MySQL: 5.7
* MySQL: 8.0
* nginx: latest
* redis: latest

## Before Installation
**Volumn:** Map the working folder to WEBROOT (See in php service in docker-compose.yml)
**MySQL Users:** Set database, user/password and root password (See in mysql service in docker-compose.yml)
**Redis Password:** Specify in command (See in redis service in docker-compose.yml)

## After Installation
**MySQL**
```shell
$ docker exec -it mysql mysql -uroot -proot123
```
```mysql
USE mysql;
UPDATE `user` SET `host`='%' WHERE `user`='root' AND `host`='"%"';
GRANT ALL PRIVILEGES ON *.* TO 'homestead';
FLUSH PRIVILEGES;
```

## Installation

1.  `git clone https://github.com/tabaoman/docker-lnmr.git lnmr`
2.  `cd lnmr/docker-compose`
3.  `docker-compose build`
4.  `docker-compose up -d`
