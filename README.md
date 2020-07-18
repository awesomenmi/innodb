# MySQL - бэкап, репликация, кластер 

Запуск стенда:
```
vagrant up
vagrant ssh
```

Проверка работы контейнеров:
```
cd /vagrant
docker-compose ps
```
```
[root@docker vagrant]# docker ps
CONTAINER ID        IMAGE                       COMMAND                  CREATED             STATUS                    PORTS                                                    NAMES
d59fed9caef0        mysql/mysql-router          "/run.sh mysqlrouter"    19 minutes ago      Up 18 minutes (healthy)   6447/tcp, 64460/tcp, 0.0.0.0:6446->6446/tcp, 64470/tcp   vagrant_mysql-router_1
1de751b641c2        mysql/mysql-server:8.0.18   "/entrypoint.sh my..."   19 minutes ago      Up 19 minutes (healthy)   33060/tcp, 0.0.0.0:3303->3306/tcp                        vagrant_mysql-server-3_1
a7a04fc4e4cc        mysql/mysql-server:8.0.18   "/entrypoint.sh my..."   19 minutes ago      Up 19 minutes (healthy)   33060/tcp, 0.0.0.0:3301->3306/tcp                        vagrant_mysql-server-1_1
aed3706e6779        mysql/mysql-server:8.0.18   "/entrypoint.sh my..."   19 minutes ago      Up 19 minutes (healthy)   33060/tcp, 0.0.0.0:3302->3306/tcp                        vagrant_mysql-server-2_1
```

Проверка состояния кластера:
```
docker exec -it vagrant_mysql-server-1_1 mysqlsh --uri root@127.0.0.1
```

![alt-текст](https://github.com/awesomenmi/innodb/blob/master/Screenshot%20from%202020-07-18%2013-31-05.png)
