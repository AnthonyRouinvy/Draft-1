<!-- TITLE: Mysql -->
<!-- SUBTITLE: A quick summary of Mysql -->

# Mysql
Principales commandes


```mysql
mysql --user=root -p
mysql> show databases;
mysql> show tables;
mysql> create database flask_mysql;
mysql> use flask_mysql;
mysql> create table users (uid INT(11) AUTO_INCREMENT PRIMARY KEY, username VARCHAR(20), password VARCHAR(32), email VARCHAR(50), settings VARCHAR(32500), tracking VARCHAR(20000), ranks INT(3));
mysql> show tables;
mysql> describe users;
mysql> SELECT * FROM users;
```

### Créer une table


```mysql
mysql> CREATE TABLE User(
 userId INT NOT NULL AUTO_INCREMENT,
 userName VARCHAR(100) NOT NULL,
 password VARCHAR(40) NOT NULL,
 PRIMARY KEY(userId)
 );
```

### Insére dans une table


```mysql
mysql> insert into User values('','Admin','admin');
```

