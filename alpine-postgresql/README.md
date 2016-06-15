# PostgreSQL docker image based on Alpine Linux

# Build

```bash
$ make build
```
# Usage
For example, you can start a basic PostgreSQL server, protected by a password,
listening on port 5432 by running the following:

``
$ docker run --name some-postgresql -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=123456 -p 5432:5432 -d alpine-postgresql
```

Next, you can start you app's container while **linking** it to the PostgreSQL
container you just created giving it access to it.

```
$ docker run --name some-app --link some-postgres:postgresql -d application-that-uses-postgresql
```

Your app will now be able to access `POSTGRES_PORT_5432_TCP_ADDR` and `POSTGRES_PORT_5432_TCP_PORT` environment variables.
