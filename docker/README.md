Deploy All-in-One docker Image
------------------------------


# Desc

Build illa utils all-in-one image and run it on your machine.  
You can check out the scripts file which in [scripts](./scripts/) folder for more details.

Note:

We highly recommended deploying with our auto-deploy tools [illa-cli](https://github.com/illacloud/illa).


# Index

- [Desc](#desc)
- [Index](#index)
- [Run Official Image](#run-official-image)
- [Build Image Manually and Run](#build-image-manually-and-run)
- [Stop and Remove Container](#stop-and-remove-container)
- [Clean Postgres Database File](#clean-postgres-database-file)
- [Config Runtime Environment Variables](#config-runtime-environment-variables)

# Run Official Image

Install GNU make and type: 

```sh
make run-official-image
```

or just execute:

```sh
/bin/bash scripts/run-official-image.sh
```

this command will pull illasoft official image and run it on your docker environment.

And Login with default username **```root```** and password **```password```**.

# Build Image Manually and Run



Install GNU make (or execute shell scripts in the scripts folder manually). 

For build illa all-in-one image and run, type:

```sh
make all
```

for podman, type:

```sh
make run-by-podman
```

or execute shell scripts ```run-by-podman.sh``` in scripts folder.


# Stop and Remove Container


```sh
make stop-and-remove-container
```


# Clean Postgres Database File

*** THIS COMMAND WILL DELETE DATABSE FILE ON YOUR DISK!!! ***  
*** BACKUP, AND DO IT CAREFULLY ***  

In Default, the postgres database will storage in ```/var/lib/illa/database/postgresql/``` folder.

Run follow command for delete it.

```sh
make clean-postgres-database-file
```


# Config Runtime Environment Variables

Edit ```scripts/run.sh``` when necessary:

```sh
# postgres database password
PG_PASS=mysecretpassword

# repo home dir
ILLA_HOME_DIR=/var/lib/illa

# postgres database file storage folder
PG_VOLUMN=${ILLA_HOME_DIR}/database/postgresql
DRIVE_VOLUMN=${ILLA_HOME_DIR}/drive
```
