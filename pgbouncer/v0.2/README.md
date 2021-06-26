# mutemath966/pgbouncer:0.2

## Pre-requisites : 
* docker-compose
* docker

## Motivation :
This docker image was to build a pre-installed pgBouncer in the Postgres docker image.
* The added feature in this docker image is that, it also allows replication as a master-slave concept.

## What is PgBouncer ?
PgBouncer is a popular connection pool for PostgreSQL which, based on the configuration, creates connections and assign incoming connections requests to it in a first-come-first served manner.

## Parameter's Explaination :
* BACKUPTIME : It is the time on which the backup operation of the database will be performed.
* PGDATA : The directory which will be use for creating the config files while initializing the Postgres as a docker image.
* POSTGRESQL_USERNAME : It is the username which will be used to access the Postgres running inside the docker image.
* POSTGRESQL_PASSWORD: It is the password which will be one of the authentication parameter, for logging into the database.
* POSTGRESQL_DATABASE: It is the database which will be created while initializing the Postgres database.
* POSTGRESQL_REPLICATION_MODE : The definition which service name has to be used as a master and which as a slave
* POSTGRESQL_REPLICATION_USER : The username which handles the replication of the postgres.
* POSTGRESQL_REPLICATION_PASSWORD : The password which will be used by the slave in order to connect/communicate to the master.