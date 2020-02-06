```
docker secret create pslhello secret.txt
```

```
echo "myDBpassWORD" | docker secret create psql_pass -
```

```
docker service create --name psql --secret pslhello --secret psql_pass -e POSTGRES_PASSWORD_FILE=/run/secrets/psql_password -e POSTGRES_USER=ahmad postgres
```
```
docker container run --name postgres_health -d --health-cmd="pg_isready -U postgres || exit 1" postgres

```

```
docker container run --init  --network nodegraphqltest -p 4000:4000 ahmad4hat/start_graphql2:latest
```

postgres
```
docker container run --name testpostgres -p 5432:5432 -v ahmadgraphqlpgdata:/var/lib/postgresql/data -d -e POSTGRES_PASSWORD=123456 postgres
```
