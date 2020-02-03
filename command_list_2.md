```sh
docker image  build -t  ahmad4hat/first_node_app  .
```

```
docker container run  -p 4000:3000  --network test --name node_fromweb_ahmad  -d ahmad4hat/first_node_app
```

```
docker container run -d --name mysqlwithvolumename -e MYSQL_ALLOW_EMPTY_PASSWORD=true -v mysql-db:/var/lib/mysql mysql
```

```
docker container run -d --name bindnigin -p 80:80 -v $(pwd):/usr/share/nginx/html nginx
```

```
docker container run -d --name postgres1 -v mypostgrs:/var/lib/postgresql/data -e POSTGRES_PASSWORD=123456 postgres:10
```
