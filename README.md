# MyBatis DB 초기세팅

## DB 설계 및 테이블 
``` SQL
CREATE USER 'green'@'%' IDENTIFIED BY 'green1234';
CREATE DATABASE greendb;
GRANT ALL PRIVILEGES ON greendb.* TO 'green'@'%';

USE greendb;

DROP TABLE users;
DROP TABLE boards;

create table users(
    id int primary KEY auto_increment,
    username varchar(20),
    password varchar(20),
    email varchar(50),
    created_at TIMESTAMP
);

create table boards(
    id int primary KEY auto_increment,
    title varchar(150),
    content longtext,
    users_id int,
    created_at TIMESTAMP
);

SELECT * FROM users;
SELECT * FROM boards;

insert into users(username, password, email, created_at) values('ssar', '1234', 'ssar@nate.com', NOW());
insert into users(username, password, email, created_at) values('cos', '1234', 'cos@nate.com', NOW());
insert into users(username, password, email, created_at) values('hong', '1234', 'hong@nate.com', NOW());
COMMIT;
```