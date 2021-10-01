Redis is not a database, is just to store large JSON file, it consist of key ans value pair. It is used for catching purposes. It is stored in RAM.


SET name anjali (set/create key anjali)


GET name  


DEL name  


KEYS *


EXISTS name


FLUSHALL(delete everything)


ttl name(get the remaining time of key expiry in seconds)


Expire name 10(will expire the key in 10 sec)   -2 defines that key has been expired


Setex name 10 anjali (set name along with expiry)

 
lpush(pushing at  extreme left )


rpush(pushing at  extreme right)


[ lpush name key ]


[rpush name key]



🔥NOTE :-> PostgreSQL is a relational database, first and foremost, whereas Redis is a key-value store.
That said, you could use PostgreSQL as a key-value store, simply because many relational database products do not dictate that you use the relational model



🏁PostgreSQL (pronounced as post-gress-Q-L) is an open source relational database management system

POSTGRESQL INIT COMMANDS :
sudo service postgresql start
psql -U postgres

CREATE DATABASE devs;                               [DON'T FORGET TO ADD ; 🔴]

  List of databases
   Name    |  Owner   | Encoding | Collate |  Ctype  |   Access privileges

-----------+----------+----------+---------+---------+-----------------------
 devs      | postgres | UTF8     | C.UTF-8 | C.UTF-8 |
 postgres  | postgres | UTF8     | C.UTF-8 | C.UTF-8 |
 template0 | postgres | UTF8     | C.UTF-8 | C.UTF-8 | =c/postgres          +
           |          |          |         |         | postgres=CTc/postgres
 template1 | postgres | UTF8     | C.UTF-8 | C.UTF-8 | =c/postgres          +
           |          |          |         |         | postgres=CTc/postgres
(4 rows)

|mark: ...skipping...

CREATE DATABASE backendclass;
postgres=# DROP DATABASE backendclass;
DROP DATABASE

postgres=# \c devs                                    [TO CONNECT TO devs databse 🔰]
You are now connected to database "devs" as user "postgres".
devs=# CREATE TABLE COMPANY(                          [Creating Table name COMPANY , TABLE NAME IS CASE INSENSITIVE ✅]
devs(# ID INT NOT NULL,             
devs(# NAME CHAR[50],
devs(# AGE INT,
devs(# ADDRESS TEXT
devs(# );
CREATE TABLE
devs=# \d                                              [\d means display👀]
          List of relations
 Schema |  Name   | Type  |  Owner
--------+---------+-------+----------
 public | company | table | postgres
(1 row)

devs=# \d COMPANY
                  Table "public.company"
 Column  |      Type      | Collation | Nullable | Default
---------+----------------+-----------+----------+---------
 id      | integer        |           | not null |
 name    | character(1)[] |           |          |
 age     | integer        |           |          |
 address | text           |           |          |

devs=# DROP TABLE COMPANY;
DROP TABLE
devs=# \d company                                   [MEANS TABLE COMPANY IS DELETED NOW 👍]
Did not find any relation named "company".

