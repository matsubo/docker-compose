Docker compose sample
=====

Abstract
---

- Building dev servers on local machine
- boot2docker +  Debian container (Redis, MySQL, Postfix)
- Used Docker Compose (New version of fig).



Initial setup
---

- install docker, docker compose  and boot2docker
```
% brew install boo2docker docker docker-compose
```



Start
---

- start host vm and set environment variables.
```
% boot2docker up
% `boot2docker shellinit`
```

- start containers
```
% docker-compose up
or
% docker-compose up -d # daemon mode
```


Show information
===

- show containers
```

% docker ps
CONTAINER ID        IMAGE                         COMMAND                CREATED             STATUS              PORTS                          NAMES
77119d9a4dfd        composetest_mysql:latest     "/usr/local/bin/run"   5 seconds ago       Up 2 seconds        0.0.0.0:3306->3306/tcp         composetest_mysql_1
73ecfbc4f886        composetest_redis:latest     "/usr/bin/redis-serv   6 seconds ago       Up 3 seconds        0.0.0.0:6379->6379/tcp         composetest_redis_1
d72f97fac9ba        composetest_postfix:latest   "sh -c 'service rsys   8 seconds ago       Up 4 seconds        25/tcp, 0.0.0.0:25->8025/tcp   composetest_postfix_1
```



- show host ip address

```
% boot2docker ip
192.168.59.104
```


Halt
===


```
% boot2docker halt
```


Issues
===
- Map containers' port into host OS.
  - https://github.com/boot2docker/boot2docker-cli#configuration
