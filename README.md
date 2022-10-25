# sqlAssignment

// create database
mysql> create database assignment

//creat table
mysql> create table Movies (
    -> ID INT(20) unsigned NOT NULL AUTO_INCREMENT,
    -> Title varchar(100),
    -> Runtime INT(200),
    -> Genre varchar(200),
    -> IMDB_Score DECIMAL(6,1) NOT NULL DEFAULT 99999.9,
    -> Rating varchar(100),
    -> PRIMARY KEY (ID)
    -> );
    //Table before
    mysql> describe Movies
    -> ;
    
+------------+--------------+------+-----+---------+----------------+
| Field      | Type         | Null | Key | Default | Extra          |
+------------+--------------+------+-----+---------+----------------+
| ID         | int unsigned | NO   | PRI | NULL    | auto_increment |
| Title      | varchar(100) | YES  |     | NULL    |                |
| Runtime    | int          | YES  |     | NULL    |                |
| Genre      | varchar(200) | YES  |     | NULL    |                |
| IMDB_Score | decimal(6,1) | NO   |     | 99999.9 |                |
| Rating     | varchar(100) | YES  |     | NULL    |                |
+------------+--------------+------+-----+---------+----------------+
```

// Adding data
mysql> INSERT INTO Movies VALUES (1, 'Howard the Duck', 110, 'Sci-Fi', 4.6, 'PG'),
    -> (2,'Lavalantula',83,'Horror',4.7,'TV-14'),
    -> (3,'Startship Troopers', 129, 'Sci-Fi', 7.2, 'PG-13'),
    -> (4,'Waltz With Bashir', 90, 'Documentary',8.0,'R'),
    -> (5,'Spaceballs', 96, 'Comedy', 7.1, 'PG'),
    -> (6, 'Monsters Inc.', 92, 'Animation',8.1,'G');
Query OK, 6 rows affected (0.01 sec)

```
+----+--------------------+---------+-------------+------------+--------+
| ID | Title              | Runtime | Genre       | IMDB_Score | Rating |
+----+--------------------+---------+-------------+------------+--------+
|  1 | Howard the Duck    |     110 | Sci-Fi      |        4.6 | PG     |
|  2 | Lavalantula        |      83 | Horror      |        4.7 | TV-14  |
|  3 | Startship Troopers |     129 | Sci-Fi      |        7.2 | PG-13  |
|  4 | Waltz With Bashir  |      90 | Documentary |        8.0 | R      |
|  5 | Spaceballs         |      96 | Comedy      |        7.1 | PG     |
|  6 | Monsters Inc.      |      92 | Animation   |        8.1 | G      |
+----+--------------------+---------+-------------+------------+--------+
```

// adding two movies of our own
 INSERT INTO Movies VALUES(NUll,'Fast furious', 120, 'Action',9.5, 'PG-13');
Query OK, 1 row affected (0.01 sec)

mysql>INSERT Int
Query OK, 1 row affected (0.01 sec)

mysql> select * from Movies
```
    -> ;
+----+--------------------+---------+-------------+------------+--------+
| ID | Title              | Runtime | Genre       | IMDB_Score | Rating |
+----+--------------------+---------+-------------+------------+--------+
|  1 | Howard the Duck    |     110 | Sci-Fi      |        4.6 | PG     |
|  2 | Lavalantula        |      83 | Horror      |        4.7 | TV-14  |
|  3 | Startship Troopers |     129 | Sci-Fi      |        7.2 | PG-13  |
|  4 | Waltz With Bashir  |      90 | Documentary |        8.0 | R      |
|  5 | Spaceballs         |      96 | Comedy      |        7.1 | PG     |
|  6 | Monsters Inc.      |      92 | Animation   |        8.1 | G      |
|  7 | Fast furious       |     120 | Action      |        9.5 | PG-13  |
|  8 | Cars               |     130 | Action      |        9.5 | PG     |
+----+--------------------+---------+-------------+------------+--------+
```

//Sci-FI
mysql>  select * from Movies WHERE Genre LIKE 'SCI__%';
```
+--------------------+---------+--------+------------+--------+
| Title              | Runtime | Genre  | IMDB_Score | Rating |
+--------------------+---------+--------+------------+--------+
| Howard the Duck    |     110 | Sci-FI |       4.60 | PG     |
| Startship Troopers |     129 | Sci-FI |       7.20 | PG-13  |
+--------------------+---------+--------+------------+--------+
```

//at least 6.5
mysql> select * from Movies Where IMDB_Score >= 6.5;
```

+----+--------------------+---------+-------------+------------+--------+
| ID | Title              | Runtime | Genre       | IMDB_Score | Rating |
+----+--------------------+---------+-------------+------------+--------+
|  3 | Startship Troopers |     129 | Sci-Fi      |        7.2 | PG-13  |
|  4 | Waltz With Bashir  |      90 | Documentary |        8.0 | R      |
|  5 | Spaceballs         |      96 | Comedy      |        7.1 | PG     |
|  6 | Monsters Inc.      |      92 | Animation   |        8.1 | G      |
|  7 | Fast furious       |     120 | Action      |        9.5 | PG-13  |
|  8 | Cars               |     130 | Action      |        9.5 | PG     |
+----+--------------------+---------+-------------+------------+--------+
```

//
