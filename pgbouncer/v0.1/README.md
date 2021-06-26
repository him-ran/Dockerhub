# mutemath966/pgbouncer:0.1

## Pre-requisites : 
* docker-compose
* docker

## Motivation :
This docker image was to build a pre-installed pgBouncer in the Postgres docker image.

## What is PgBouncer ?
PgBouncer is a popular connection pool for PostgreSQL which, based on the configuration, creates connections and assign incoming connections requests to it in a first-come-first served manner.

## Parameter's Explaination :
* BACKUPTIME : It is the time on which the backup operation of the database will be performed.
* PGDATA : The directory which will be use for creating the config files while initializing the Postgres as a docker image.
* POSTGRES_USERNAME : It is the username which will be used to access the Postgres running inside the docker image.
* POSTGRES_PASSWORD: It is the password which will be one of the authentication parameter, for logging into the database.
* POSTGRES_DB: It is the database which will be created while initializing the Postgres database.

### NOTE :
* By default the Postgres runs on the 5432 port.
* But in this docker image we are exposing the 6432 port for the docker image.
* The reason behind this is that, we want to direct the requests made to postgres to 6432 port which is the port on which PgBouncer has its servic running on.
* So, in order to involve PgBouncer as part of the storage/retrieval mechanism, we expose the 6432 port for accessing the service.

### More Info : 
* This postgres will run with max_connections as 500.
* The PgBouncer also has the default pool size as 500, if you use the pgbouncer.ini files provided in the GIT repository.

## Command-Line Execution
```
docker run -d \
-v ${PATH_TO_PGBOUNCER.INI}:/etc/pgbouncer/pgbouncer.ini \
-v ${PATH_TO_USERLIST.TXt}:/etc/pgbouncer/userlist.txt \
-p 5432:5432 \
-p 6432:6432 \
-e POSTGRES_PASSWORD=${POSTGRES_PASSWORD} \
mutemath966/pgbouncer:0.1
```
