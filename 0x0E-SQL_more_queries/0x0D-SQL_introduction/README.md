# 0x0D. SQL - Introduction
 Foundations > Higher-level programming > Databases


## General
* Allowed editors: vi, vim, emacs
* All your files will be executed on Ubuntu 14.04 LTS using MySQL 5.7 (version 5.7.8-rc)
* All your files should end with a new line
* All your SQL queries should have a comment just before (i.e. syntax above)
* All your files should start by a comment describing the task
* All SQL keywords should be in uppercase (SELECT, WHERE…)
* A README.md file, at the root of the folder of the project, is mandatory
* The length of your files will be tested using wc


## Comments for your SQL file:

```
$ cat my_script.sql
-- 3 first students in the Batch ID=3
-- because Batch 3 is the best!
SELECT id, name FROM students WHERE batch_id = 3 ORDER BY created_at DESC LIMIT 3;
$
```

## Install MySQL 5.7 on Ubuntu 14.04 LTS 

```
$ echo 'deb http://repo.mysql.com/apt/ubuntu/ trusty mysql-5.7-dmr' | sudo tee -a /etc/apt/sources.list
$ sudo apt-get update
$ sudo apt-get install mysql-server-5.7
...
$ mysql --version
mysql  Ver 14.14 Distrib 5.7.8-rc, for Linux (x86_64) using  EditLine wrapper
$
```


## Connect to your MySQL server:

```
$ mysql -hlocalhost -uroot -p
Password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 42
Server version: 5.7.8-rc MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 
mysql> quit
Bye
$
```


## Use “container-on-demand” to run MySQL

```
$ service mysql start
 * MySQL Community Server 5.7.8-rc is started
$
$ cat 0-list_databases.sql | mysql -uroot -p my_database
Enter password: 
Database
information_schema
mysql
performance_schema
sys
$
```

## Tasks

## 0. List databases  [ 0-list_databases.sql ]
  Write a script that lists all databases of your MySQL server.
> cat 0-list_databases.sql | mysql -hlocalhost -uroot -p

## 1. Create a database  [ 1-create_database_if_missing.sql ]
  Write a script that creates the database [ hbtn_0c_0 ] in your MySQL server.
* If the database hbtn_0c_0 already exists, your script should not fail
* You are not allowed to use the SELECT or SHOW statements
> cat 1-create_database_if_missing.sql | mysql -hlocalhost -uroot -p

> cat 0-list_databases.sql | mysql -hlocalhost -uroot -p

> cat 1-create_database_if_missing.sql | mysql -hlocalhost -uroot -p

## 2. Delete a database  [ 2-remove_database.sql ]
  Write a script that deletes the database [ hbtn_0c_0 ] in your MySQL server.
* If the database hbtn_0c_0 doesn’t exist, your script should not fail
* You are not allowed to use the SELECT or SHOW statements
> cat 0-list_databases.sql | mysql -hlocalhost -uroot -p

> cat 2-remove_database.sql | mysql -hlocalhost -uroot -p

> cat 0-list_databases.sql | mysql -hlocalhost -uroot -p

## 3. List tables  [ 3-list_tables.sql ]
  Write a script that lists all the tables of a database in your MySQL server.
* The database name will be passed as argument of mysql command (in the following example: mysql is the name of the database)
> cat 3-list_tables.sql | mysql -hlocalhost -uroot -p mysql

## 4. First table  [ 4-first_table.sql ]
  Write a script that creates a table called first_table in the current database in your MySQL server.
* first_table description:
		id INT
		name VARCHAR(256)
* The database name will be passed as an argument of the mysql command
* If the table first_table already exists, your script should not fail
* You are not allowed to use the SELECT or SHOW statements
> cat 4-first_table.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

> cat 3-list_tables.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 5. Full description  [ 5-full_table.sql ]
  Write a script that prints the full description of the table first_table from the database hbtn_0c_0 in your MySQL server.
* The database name will be passed as an argument of the mysql command
* You are not allowed to use the DESCRIBE or EXPLAIN statements
> cat 5-full_table.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 6. List all in table  [ 6-list_values.sql ]
  Write a script that lists all rows of the table first_table from the database hbtn_0c_0 in your MySQL server.
* All fields should be printed
* The database name will be passed as an argument of the mysql command
> cat 6-list_values.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 7. First add  [ 7-insert_value.sql ]
  Write a script that inserts a new row in the table first_table (database hbtn_0c_0) in your MySQL server.
* New row:
		id = 89
		name = Holberton School
* The database name will be passed as an argument of the mysql command
> cat 7-insert_value.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

> cat 6-list_values.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

> cat 7-insert_value.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

> cat 7-insert_value.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

> cat 6-list_values.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 8. Count 89  [ 8-count_89.sql ]
  Write a script that displays the number of records with id = 89 in the table first_table of the database hbtn_0c_0 in your MySQL server.
* The database name will be passed as an argument of the mysql command
> cat 8-count_89.sql | mysql -hlocalhost -uroot -p hbtn_0c_0 | tail -1

## 9. Full creation  [ 9-full_creation.sql ]
  Write a script that creates a table second_table in the database hbtn_0c_0 in your MySQL server and add multiples rows.
* second_table description:
		id INT
		name VARCHAR(256)
		score INT
* The database name will be passed as an argument to the mysql command
* If the table second_table already exists, your script should not fail
* You are not allowed to use the SELECT and SHOW statements
* Your script should create these records:
		id = 1, name = “John”, score = 10
		id = 2, name = “Alex”, score = 3
		id = 3, name = “Bob”, score = 14
		id = 4, name = “George”, score = 8
> cat 9-full_creation.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 10. List by best  [ 10-top_score.sql ]
  Write a script that lists all records of the table second_table of the database hbtn_0c_0 in your MySQL server.
* Results should display both the score and the name (in this order)
* Records should be ordered by score (top first)
* The database name will be passed as an argument of the mysql command
> cat 10-top_score.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 11. Select the best  [ 11-best_score.sql ]
  Write a script that lists all records with a score >= 10 in the table second_table of the database hbtn_0c_0 in your MySQL server.
* Results should display both the score and the name (in this order)
* Records should be ordered by score (top first)
* The database name will be passed as an argument of the mysql command
> cat 11-best_score.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 12. Cheating is bad  [ 12-no_cheating.sql ]
  Write a script that updates the score of Bob to 10 in the table second_table.
* You are not allowed to use Bob’s id value, only the name field
* The database name will be passed as an argument of the mysql command
> cat 12-no_cheating.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

> cat 10-top_score.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 13. Score too low  [ 13-change_class.sql ]
  Write a script that removes all records with a score <= 5 in the table second_table of the database hbtn_0c_0 in your MySQL server.
* The database name will be passed as an argument of the mysql command
> cat 13-change_class.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

> cat 10-top_score.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 14. Average  [ 14-average.sql ]
  Write a script that computes the score average of all records in the table second_table of the database hbtn_0c_0 in your MySQL server.
* The result column name should be average
* The database name will be passed as an argument of the mysql command
> cat 14-average.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 15. Number by score  [ 15-groups.sql ]
  Write a script that lists the number of records with the same score in the table second_table of the database hbtn_0c_0 in your MySQL server.
* The result should display:
		the score
		the number of records for this score with the label number
* The list should be sorted by the number of records (descending)
* The database name will be passed as an argument to the mysql command
> cat 15-groups.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 16. Say my name  [ 16-no_link.sql ]
  Write a script that lists all records of the table second_table of the database hbtn_0c_0 in your MySQL server.
* Don’t list rows without a name value
* Results should display the score and the name (in this order)
* Records should be listed by descending score
* The database name will be passed as an argument to the mysql command

In this example, new data have been added to the table second_table.
> cat 16-no_link.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 17. Go to UTF8  [ 100-move_to_utf8.sql ]
  Write a script that converts hbtn_0c_0 database to UTF8 (utf8mb4, collate utf8mb4_unicode_ci) in your MySQL server.

You need to convert all of the following to UTF8:
* Database hbtn_0c_0
* Table first_table
* Field name in first_table
> cat 100-move_to_utf8.sql | mysql -hlocalhost -uroot -p 

> cat 5-full_table.sql | mysql -hlocalhost -uroot -p hbtn_0c_0


## 18. Temperatures #0  [ 101-avg_temperatures.sql ]
  Import in hbtn_0c_0 database this table dump: [download](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/272/temperatures.sql)

Write a script that displays the average temperature (Fahrenheit) by city ordered by temperature (descending).
> cat 101-avg_temperatures.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 19. Temperatures #1  [ 102-top_city.sql ]
  Write a script that displays the top 3 of cities temperature during July and August ordered by temperature (descending)
> cat 102-top_city.sql | mysql -hlocalhost -uroot -p hbtn_0c_0

## 20. Temperatures #2  [ 103-max_state.sql ]  
  Write a script that displays the max temperature of each state (ordered by State name).
> cat 103-max_state.sql | mysql -hlocalhost -uroot -p hbtn_0c_0  

## Resources

Read or watch:

* [What is Database & SQL?](https://www.youtube.com/watch?v=FR4QIeZaPeM)
* [A Basic MySQL Tutorial](https://www.digitalocean.com/community/tutorials/a-basic-mysql-tutorial)
* [Basic SQL statements: DDL and DML](https://web.csulb.edu/colleges/coe/cecs/dbdesign/dbdesign.php?page=sql/ddldml.php) (no need to read the chapter “Privileges”)]()
* [Basic queries: SQL and RA](https://web.csulb.edu/colleges/coe/cecs/dbdesign/dbdesign.php?page=sql/queries.php)
* [SQL technique: functions](https://web.csulb.edu/colleges/coe/cecs/dbdesign/dbdesign.php?page=sql/functions.php)
* [SQL technique: subqueries](https://web.csulb.edu/colleges/coe/cecs/dbdesign/dbdesign.php?page=sql/subqueries.php)
* [What makes the big difference between a backtick and an apostrophe?](https://stackoverflow.com/questions/29402361/what-makes-the-big-difference-between-a-backtick-and-an-apostrophe/29402458)
* [MySQL Cheat Sheet](https://intellipaat.com/mediaFiles/2019/02/SQL-Commands-Cheat-Sheet.pdf)
* [MySQL 5.7 SQL Statement Syntax](https://dev.mysql.com/doc/refman/5.7/en/sql-statements.html)


