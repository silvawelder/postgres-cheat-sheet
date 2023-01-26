# postgres-cheat-sLogin on PostgreSQL Host to do Administration commands

Log in PostgreSQL host and input command bellow:

```sudo su postgres```

Enter with the bellow command to access PostgreSQL command line utility:

```psql```



Database

How to create a new database

command:

```create database <database-name>;```

sample:

```create database my_database;```

How to list all databases

```\l```

How to use a database

command:

```\c database-name```

sample:

```create database my_database;```

Tables

How to list all tables

```\dt *.*```

How to list all tables from a schema

command:

```\dt schema_name.*```

sample

```\dt my_schema.*```

How to delete a table from a schema

command:

```DROP TABLE <schema_name>.<table_name>;```

sample:

```DROP TABLE my_schema.table_users;```

How to delete all tables from a schema

command:

```DROP SCHEMA schema_name CASCADE;```

sample:

```DROP SCHEMA my_schema CASCADE;```

Users
How to create a new user

command:

```create user <user-name>;```

sample:

```create user my_user;```

How to create a password to an user

command:

```alter user my_user with encrypted password '<input-password-here>';```

sample:

```alter user my_user with encrypted password 'p455w0rd';```

Grant privileges to an user:

command:

```grant all privileges on database <database-name> to <user-name>;```

sample:

```grant all privileges on database my_database to my_user;```

Listando todos os usuários

```\du```



Manipulating connections

command to list number of active connections and max connections

```SELECT current_setting('max_connections') AS max, COUNT(*) AS total FROM pg_stat_activity;```

command to kill active connections

```SELECT pg_terminate_backend(pg_stat_activity.pid) FROM pg_stat_activity WHERE pg_stat_activity.datname = '<database-name>' AND pid <> pg_backend_pid();```
