## MySQL Administration - Import/Load the database

**MySQL Import from Command line**

In this post, let us see how to import the .sql file to the database. 

```
C:\Users\ragha\Desktop\Website DB Backups
λ ls -ltrh
total 3.9M
-rw-r--r-- 1 raghs 197610 1.8M Nov  2 23:13 shade.sql
-rw-r--r-- 1 raghs 197610 252K Nov  2 23:13 shade.sql.zip
-rw-r--r-- 1 raghs 197610 242K Nov  2 23:13 shade.csv.zip
-rw-r--r-- 1 raghs 197610 1.7M Nov  2 23:14 shade.csv
```

Beforehand, we should create the database if it does not exist. Otherwise, drop it and recreate it so that it can accommodate the files what we want to load to all the tables in the database. 

Note: It depends on the export script. If the script has got the drop and recreate the database, we do not need to do it explicitly/manually. 

```
C:\Users\ragha\Desktop\Website DB Backups
λ mysql -u raghs -p
Enter password: *************
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 2059
Server version: 10.1.13-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2016, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show tables;
ERROR 1046 (3D000): No database selected
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| easytodo           |
| hibernatedb        |
| information_schema |
| itsraghz           |
| mysql              |
| performance_schema |
| phpmyadmin         |
| shade              |
| simpletodo         |
| tamiltest          |
| test               |
+--------------------+
11 rows in set (0.00 sec)

MariaDB [(none)]> drop database shade;
Query OK, 28 rows affected (3.23 sec)

MariaDB [(none)]> create database shade;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> exit
Bye
```

Now let us import the sql dump for the database. 

```
C:\Users\ragha\Website DB Backups
λ mysql -u raghs -p shade < shade.sql
Enter password: *************

C:\Users\ragha\Website DB Backups
λ
```

If there are no messages in the console, it means the import was successful. You can login to MySQL client and verify the table structure and/or the data of your choice.