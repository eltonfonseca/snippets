# Some Snippets

## UP databases with docker

### MySQL 8
```bash
docker run --name local_mysql8 -v mysql8:/var/lib/mysql --network local -p 3306:3306 -e MYSQL_ALLOW_EMPTY_PASSWORD=true mysql:8.0 
```
### MySQL 5.7
```bash
docker run --name local_mysql5 --platform=linux/x86_64 -v mysql5:/var/lib/mysql --network local -p 3306:3306 -e MYSQL_ALLOW_EMPTY_PASSWORD=true mysql:5.7 mysqld --character-set-server=utf8 --collation-server=uft8_unicode_ci --init-connect='SET NAMES UTF8;' --innodb-flush-log-at-trx-commit=0
```

### PostgreSQL 12
```bash
docker run --name local_postgres -v postgres:/var/lib/postgresql --network local -p 5432:5432 -e POSTGRES_HOST_AUTH_METHOD=trust -e POSTGRES_PASSWORD='admin' -e POSTGRES_USER='admin' postgres:12 
```

### Mail catcher
```bash
docker run --name local_email -d --network local -p 1080:1080 -p 1025:1025 schickling/mailcatcher
```

### Redis
```bash
docker run --name local_redis -d --network local -p 6379:6379 redis
```
