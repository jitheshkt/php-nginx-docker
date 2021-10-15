# php-nginx-docker
## Web server
```
docker build -t php-nginx:latest .
```
## Bring the container online
```
docker-compose up -d
```
## Configure mysql connection
MySQL access will be restricted by default for root user. You have to create a user by terminaling into the container and running the below query.
```
docker exec -it mysql1 mysql -uroot -p
CREATE USER 'myuser'@'%' IDENTIFIED BY 'mypass';
GRANT ALL ON *.* TO 'myuser'@'%';
FLUSH PRIVILEGES;
```

Use `mysql` & `redis` as `host` for connecting to MySQL or Redis from PHP.