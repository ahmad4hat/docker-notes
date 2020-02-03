> Creates a docker container with nginx image on port 80

```terminal
docker container run --publish 80:80 nginx
```

Creates a docker container with nginx image on port 80 but detached from the terminal

```terminal
docker container run --publish 80:80 --detach nginx
```

> List of containers

```terminal
docker container ls
```

> stop an container with and id =12fe54b66616f151ee4b86de9626bf2631f915e101d58520c0264a2266ca4031
> (only need fist 3 digit )

```terminal
docker container stop 12f
```

> with name continer

```terminal
docker container run --publish 80:80 --detach --name webhost  nginx
```

> logs

```terminal
docker container logs webhost
```

> give the processes running under the webshost

```terminal
docker container top webhost
```

> remove docker container

```terminal
 docker container rm a72 12f 004
```

> give the docker pocess

```terminal
docker process
```

> created a mysql container with port 3306(on my machine):3306(onDocker) detached from the terminal ,with name mysqlahmad , and enviroment variable set to "MYSQL_RANDOM_ROOT_PASSWORD=yes"

```terminal
docker container run --publish 3306:3306 -d --name mysqlahmad -e MYSQL_RANDOM_ROOT_PASSWORD=yes  mysql
```

> for stats

```terminal
docker container stats
```

> for inspecting the c9f

```terminal
docker container inspect c9f
```

> sorted log

```
 docker container top c9f
```

> running a command without stoping the previos one

```
docker container exec -it mysqlahmad bash
```

> inspect formating

```
docker container inspect --format '{{.NetworkSettings.IPAddress }}' nignx
```

> port number of the container

```
docker container port
```

# Network

> list of network

```
docker network ls
```

> check the default network

```
docker network inspect bridge
```

> create a nginx container called **new_nginx** in network **my_newwork**

```
docker container run -d --name new_nginx --network my_network nginx
```

> conncect container **c9f17392c9fa** to network **my_network**

```
docker network connect my_network c9f17392c9fa
```

> disconncect container **c9f17392c9fa** to network **my_network**

```
docker network disconnect my_network c9f17392c9fa
```

> ping form one container to another , it wont work because new_nginx does not have ping

```
docker container exec -it new_nginx ping xnginx
```

> setup **ubuntu** inside an container

```
docker container run  --name ubuntu --network my_network -it ubuntu
```

start that ubuntu instance

```
 docker container start -ai ubuntu
```

round robin

```
docker network create test

docker container run -d --net test  --net-alias search elasticsearch:2

docker container run -d --net test  --net-alias search elasticsearch:2

docker container run --rm --net test  alpine nslookup search

docker container run --rm   --network test  -it ubuntu

apt-get install curl
curl -s search:9200

```
