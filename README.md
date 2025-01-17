# ConfigHub Database Manager [![Build Status](https://travis-ci.org/ConfigHubPub/Database-Manager.svg?branch=master)](https://travis-ci.org/ConfigHubPub/Database-Manager)

Before upgrading ConfigHub instances to the latest version, DBManager will upgrade your database schema to the
latest version.  ConfigHub instances starting with version 1.8 will require you to upgrade the schema using
Database Manager before they will run.

### Build:
`./gradlew clean build jar`

### Run:
`java -jar build/libs/ConfigHubDBManager-1.9.1.jar [parameters]`

### Usage: 
`parameters [-hV] -t <databaseType> -r <databaseUrl> -u <username> -p <password>`

```
  -h, --help                Show this help message and exit.
  -t, --url=<databaseType>  Database types: oracle, postgresql, mysql
  -r, --url=<databaseUrl>   Database URL.  Ex: jdbc:postgresql://127.0.0.1:5432/ConfigHub
  -u, --user=<username>     Database username  
  -p, --password=<password> Database password
  -V, --version             Print version information and exit.
```

### Usage docker:

It will be specting the envs DB_USER, DB_PASSWORD, DB_TYPE, DB_URL.
This will be used inside dbm.sh

```
docker run -it --rm \
    -e DB_USER='confighub' \
    -e DB_PASSWORD='password' \
    -e DB_TYPE='mysql' \
    -e DB_URL='jdbc:mysql://ip_of_server:3306/confighub' \
    confighub/confighudbm:latest
```

