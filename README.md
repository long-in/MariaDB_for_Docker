## How to build MariaDB for Docker

### Run Docker command

```shell
$ docker run --name mariadb -v `pwd`/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=toor -p 3306:3306 -d mariadb:10.3.17-bionic
```

### Run MariaDB commands

#### Create database

```sql
CREATE DATABASE test_db;
```

#### Create table

```sql
CREATE TABLE `test_table` (
  `id` bigint(20) unsigned NOT NULL AUTO_INCREMENT,
  `created_at` datetime DEFAULT current_timestamp(),
  `updated_at` datetime DEFAULT current_timestamp() ON UPDATE current_timestamp(),
  `deleted_at` datetime DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb4 COMMENT='テストテーブル';
```


#### Create User

```sql
GRANT ALL PRIVILEGES ON *.* TO "test_user"@"0.0.0.0" IDENTIFIED BY 'test_password' WITH GRANT OPTION;
```


#### 
