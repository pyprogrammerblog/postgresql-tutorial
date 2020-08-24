# Postgresql-Tutorial

An up and running for new postgresql developers.
Short tutorial for new developers diving into SQL.

## Installing the Server Dependencies

First thing let’s upgrade the packages:
```shell
sudo apt-get update
sudo apt-get -y upgrade
```
Install the dependencies to use PostgreSQL with Python/Django:
```shell
sudo apt-get -y install build-essential libpq-dev python-dev
```
Install the PostgreSQL Server in your laptop or machine:
```shell
sudo apt-get -y install postgresql postgresql-contrib
```
then start the postgres service
```shell
service postgresql start
```
Now the service is up and running, let us jump into the postgres console (psql)...
```
sudo -i
su - postgres
```
...and create an user and db. 
```shell
createuser jose
createdb jose_db --owner jose
psql -c "ALTER USER jose WITH PASSWORD '123'"
```

## Starting with basic commands in Postgres

From postgres hit `psql` and then you are in the postgresql console:

Check version
```
SELECT version();
```

Check date
```
SELECT now();
```

List databases
```
\l
```

Now it is time to create a DATABASE!
```
CREATE DATABASE favouritecolors;
```

List databases again and see diference.
```
\l
```

Now we create a table inside our database (A table is like a sheet in an excelsheet)
```
CREATE TABLE colors (ColorID int, ColorName char(20));
```

Now store some data:
```
INSERT INTO colors VALUES (1, 'red'), (2, 'blue'), (3, 'yellow');
```

And finally we list them:
```
SELECT * FROM colors;
```
