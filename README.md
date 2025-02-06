# SQL_practice
show databases;

create database VIT;
drop database VIT;
use ViT;
create table CSE(
s_id int,
s_name varchar(30),
s_mark int
);
drop table cse;
show tables from VIt;

select * from cse;
insert into cse values (1001,'Ram Prasad',99);
desc cse;
Alter Table cse Drop column s_contact;


create database practice1;
use practice1;
create table Mech(s_id int,s_name varchar(25));
START TRANSACTION;
insert into Mech values (101,'jayanth')




CREATE DATABASE ORG123;
SHOW DATABASES;
USE ORG123;

CREATE TABLE Worker (
    WORKER_ID INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    FIRST_NAME CHAR(25),
    LAST_NAME CHAR(25),
    SALARY INT,
    JOINING_DATE DATETIME,
    DEPARTMENT CHAR(25)
);

INSERT INTO Worker 
(WORKER_ID, FIRST_NAME, LAST_NAME, SALARY, JOINING_DATE, DEPARTMENT) VALUES
    (1, 'Monika', 'Arora', 100000, '2020-02-14 09:00:00', 'HR'),
    (2, 'Niharika', 'Verma', 80000, '2011-06-14 09:00:00', 'Admin'),
    (3, 'Vishal', 'Singhal', 300000, '2020-02-14 09:00:00', 'HR'),
    (4, 'Amitabh', 'Singh', 500000, '2020-02-14 09:00:00', 'Admin'),
    (5, 'Vivek', 'Bhati', 500000, '2011-06-11 09:00:00', 'Admin'),
    (6, 'Vipul', 'Diwan', 200000, '2011-06-11 09:00:00', 'Account'),
    (7, 'Satish', 'Kumar', 75000, '2020-01-14 09:00:00', 'Account'),
    (8, 'Geetika', 'Chauhan', 90000, '2011-04-11 09:00:00', 'Admin');
      
SELECT * FROM worker
WHERE salary BETWEEN 200000 AND 400000
AND WORKER_ID IN (1,2,3,4,5);
SELECT * FROM Worker W1
WHERE NOT EXISTS (
    SELECT 1 FROM Worker W2
    WHERE W2.DEPARTMENT = W1.DEPARTMENT AND W2.SALARY > W1.SALARY
);

use org123;
select* from worker;
select distinct(department) from worker;
#alias- help u to give some temp name fro a column

select worker_id from worker;
SELECT City FROM Customers
UNION

SELECT City FROM Suppliers
ORDER BY City;

SELECT worker_id, first_name,department,
CASE
    WHEN salary > 300000 THEN 'Rich people'
    WHEN salary <=300000 && salary >=100000 THEN 'Middle stage'
    ELSE 'Poor people'
END 
AS People_stage_wise
FROM worker;
