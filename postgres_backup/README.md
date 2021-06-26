# mutemath966/postgres_backup
This readme file tells about the changes, and the functions about the different version of the docker images of the postgres which we have in the available repo.

## v0.0.1
### Motivation :
In this version of the docker image we have created an inbuild function of the backup of the Postgres Databases. We introduced an environmental variable called BACKUPFOLDER, BACKUPTIME, DATABASENAME.

* BACKUPTIME: This will be the ENV variable which we can define at what time do we want to create a backup of the databases available in the postgres.
* DATABASENAME: The database whose backup has to be done available in the Postgres Container.

### Execution :
#### On Windows : 
```
docker run -d -e POSTGRES_PASSWORD=1234 -e BACKUPFOLDER=/backup -e BACKUPTIME="01:38:00" -e DATABASENAME=nuwebapp -v "C:\Learning\Shell\backup":"/backup" mutemath966/postgres_backup:0.1
```
#### On Linux : 
```
docker run -d -e POSTGRES_PASSWORD=1234 -e BACKUPFOLDER=/backup -e BACKUPTIME="01:38:00" -e DATABASENAME=nuwebapp -v /backup:/backup mutemath966/postgres_backup:0.1
```