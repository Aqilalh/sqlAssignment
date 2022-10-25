# sqlAssignment

// create database
mysql> create database assignment

//creat table
mysql> create table Movies (
    -> Title varchar(100),
    -> Runtime int,
    -> Genre varchar(200),
    -> IMDB_Score DECIMAL(7,2) NOT NULL DEFAULT 99999.99,
    -> Rating varchar(100),
    -> PRIMARY KEY (TITLE)
    -> );
    //Table before
    mysql> describe Movies
    -> ;
    ***
+------------+--------------+------+-----+----------+-------+
| Field      | Type         | Null | Key | Default  | Extra |
+------------+--------------+------+-----+----------+-------+
| Title      | varchar(100) | NO   | PRI | NULL     |       |
| Runtime    | int          | YES  |     | NULL     |       |
| Genre      | varchar(200) | YES  |     | NULL     |       |
| IMDB_Score | decimal(7,2) | NO   |     | 99999.99 |       |
| Rating     | varchar(100) | YES  |     | NULL     |       |
+------------+--------------+------+-----+----------+-------+
***

// Adding data
mysql> INSERT INTO Movies VALUES ('Howard the Duck', 110, 'Sci-FI', 4.6, 'PG'),
    -> ('Lavalantula',83,'Horror',4.7, 'TV-14'),
    -> ('Startship Troopers', 129, 'Sci-FI',7.2,'PG-13'),
    -> ('Waltz With Bashir', 90, 'Documentary',8.0,'R'),
    -> ('Spaceballs', 96, 'Comedy', 7.1,'PG'),
    -> ('Monsters Inc.', 92, 'Animation', 8.1, 'G');
Query OK, 6 rows affected (0.21 sec)

***
+--------------------+---------+-------------+------------+--------+
| Title              | Runtime | Genre       | IMDB_Score | Rating |
+--------------------+---------+-------------+------------+--------+
| Howard the Duck    |     110 | Sci-FI      |       4.60 | PG     |
| Lavalantula        |      83 | Horror      |       4.70 | TV-14  |
| Monsters Inc.      |      92 | Animation   |       8.10 | G      |
| Spaceballs         |      96 | Comedy      |       7.10 | PG     |
| Startship Troopers |     129 | Sci-FI      |       7.20 | PG-13  |
| Waltz With Bashir  |      90 | Documentary |       8.00 | R      |
+--------------------+---------+-------------+------------+--------+
***

// adding two movies of our own
 INSERT INTO Movies VALUES('Fast furious', 120, 'Action',9.5, 'PG-13');
Query OK, 1 row affected (0.01 sec)

mysql> INSERT INTO Movies VALUES('Cars', 120, 'Action',10.0, 'PG');
Query OK, 1 row affected (0.01 sec)

***
+--------------------+---------+-------------+------------+--------+
| Title              | Runtime | Genre       | IMDB_Score | Rating |
+--------------------+---------+-------------+------------+--------+
| Cars               |     120 | Action      |      10.00 | PG     |
| Fast furious       |     120 | Action      |       9.50 | PG-13  |
| Howard the Duck    |     110 | Sci-FI      |       4.60 | PG     |
| Lavalantula        |      83 | Horror      |       4.70 | TV-14  |
| Monsters Inc.      |      92 | Animation   |       8.10 | G      |
| Spaceballs         |      96 | Comedy      |       7.10 | PG     |
| Startship Troopers |     129 | Sci-FI      |       7.20 | PG-13  |
| Waltz With Bashir  |      90 | Documentary |       8.00 | R      |
+--------------------+---------+-------------+------------+--------+
***

//Sci-FI
mysql>  select * from Movies WHERE Genre LIKE 'SCI__%';
***
+--------------------+---------+--------+------------+--------+
| Title              | Runtime | Genre  | IMDB_Score | Rating |
+--------------------+---------+--------+------------+--------+
| Howard the Duck    |     110 | Sci-FI |       4.60 | PG     |
| Startship Troopers |     129 | Sci-FI |       7.20 | PG-13  |
+--------------------+---------+--------+------------+--------+
***

//at least 6.5
mysql> select * from Movies Where IMDB_Score >= 6.5;
***
+--------------------+---------+-------------+------------+--------+
| Title              | Runtime | Genre       | IMDB_Score | Rating |
+--------------------+---------+-------------+------------+--------+
| Cars               |     120 | Action      |      10.00 | PG     |
| Fast furious       |     120 | Action      |       9.50 | PG-13  |
| Monsters Inc.      |      92 | Animation   |       8.10 | G      |
| Spaceballs         |      96 | Comedy      |       7.10 | PG     |
| Startship Troopers |     129 | Sci-FI      |       7.20 | PG-13  |
| Waltz With Bashir  |      90 | Documentary |       8.00 | R      |
+--------------------+---------+-------------+------------+--------+
***
