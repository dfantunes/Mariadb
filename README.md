
# **Mariadb**

How [Install Mariadb on Linux](https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04-pt/) ?


# Connecting to Mariadb 

 After the installation we can connect with Mariadb through the command line:


```bash
sudo mariadb
```
```sql
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 40
Server version: 10.1.47-MariaDB-0ubuntu0.18.04.1 Ubuntu 18.04
Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
``` 


## Checking if exists any database

```sql
SHOW DATABASES;

MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.00 sec)
```

## Creating a new database
```sql
CREATE DATABASE TEST;
```
>Note: We can put database name between **``** or not.
```sql
Query OK, 1 row affected (0.00 sec)
```

```sql
MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| TEST               |
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
4 rows in set (0.01 sec)
```
## Referencing the created database

```sql
MariaDB [mysql]> USE TEST;
Database changed
MariaDB [TEST]>
```

## Checking if exists any table on database.
```sql
MariaDB [TEST]> SHOW TABLES;
Empty set (0.00 sec)
```

## Creating a new table on database


```sql
MariaDB [TEST]> DROP TABLE IF EXISTS `Cars`;
Query OK, 0 rows affected, 1 warning (0.00 sec)

MariaDB [TEST]>     CREATE TABLE `Cars` (
        `Make` VARCHAR(50) NULL DEFAULT NULL,
         `Model` VARCHAR(255) NULL DEFAULT NULL,
          `Type` VARCHAR(50) NULL DEFAULT NULL,
         `Origin` VARCHAR(50) NULL DEFAULT NULL,
          `DriveTrain` VARCHAR(50) NULL DEFAULT NULL,
         `Lenght` INT NULL
          )
         COLLATE='latin1_swedish_ci'
        ;
Query OK, 0 rows affected (0.06 sec)
```
> Note: the Collate type can be changed for a necessity. For more information check: [Collation Settings](https://mariadb.com/kb/en/setting-character-sets-and-collations/) 


# Verifying that the table has been created

```SQL
MariaDB [TEST]> SHOW TABLES;
+----------------+
| Tables_in_TEST |
+----------------+
| Cars           |
+----------------+
1 row in set (0.00 sec)
```
