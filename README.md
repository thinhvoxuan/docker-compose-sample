# docker-compose-sample
**Problem:** I need some service run on my computer without installing. Docker could help me do that. I use many docker images from `mysql`, `rethinkdb`, `rabbitmq`, ...

**Solve:** Sample `docker-compose.yml` file for each service (or Data Service) at **[https://github.com/voxuanthinh/docker-compose-sample](https://github.com/voxuanthinh/docker-compose-sample)**

How to use: copy that config from my repository and merge it into one file, then use `links` and `depends_on` to connect that services.

```

version: '2'
services:
  gupm:
    image: xuanthinh244/docker-phalcon:v3.0.0
    container_name: phalcon
    volumes:
      - ./src:/var/www/phalcon/
      - ./src/log:/var/log/apache2
    ports:
      - 7171:80
    environment:
      - ALLOW_OVERRIDE=true
      - APPLICATION_ENV=development
    links:
      - mysql:mysql
    depends_on:
      - mysql
  mysql:
      image: mysql
      container_name: mysql
      environment:
        - MYSQL_ROOT_PASSWORD=gu123451
      ports:
        - 3306:3306
      volumes:
        - ./db:/var/lib/mysql
        - ./db/initscript:/docker-entrypoint-initdb.d
      command: mysqld --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci

```


Ref: [https://docs.docker.com/compose/](https://docs.docker.com/compose/)

From: [http://thinhvoxuan.me/docker-compose-sample/](http://thinhvoxuan.me/docker-compose-sample/)


