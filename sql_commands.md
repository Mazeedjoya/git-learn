
### SYLLABUS 
```
MySQL -> MongoDB -> Web -> Rest APIs theory -> Nodejs Basics -> Nodejs Advanced with REST APIs -> CRUD Operations - Mysql and MongoDB in Nodejs
```
## MySQL Commands

### Create Database

```
create database wecodeacademy;
```

### Show Databases

```
show databases;
```

### Select Database

```
use wecodeacademy;
```
### Show Databases
```
show databases;
```
### Drop Database
```
drop database name;
```

### Create Table

```
CREATE TABLE `student` ( 
 `studentid` int(10) UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT, 
 `name` varchar(255) , 
 `email_address` varchar(255), 
 `city` varchar(255) , 
 `fathername` varchar(255),
 `mobile` int(15)
);
```

### Show Tables

```
show tables;
```

### Select All Columns from a table

```
select * from student;
```

### Select specific columns from a table

```
select name, mobile from student;
```

### Insert into table using column names

```
INSERT INTO student (name, email_address, city, fathername, mobile) VALUES ('Shera' ,'sher.badnam@gmail.com', 'Merta', 'Kalam Khan',  999999999);
```

### Insert into table without using column names

```
INSERT INTO student VALUES (1, 'Shera' ,'sher.badnam@gmail.com', 'Merta', 'Kalam Khan',  999999999);
```

### Where Condition examples

```
select * from student where name  = 'Sajid' or studentid  = 2;

select * from student where name  = 'Sajid' and studentid  = 2;
```

### distinct

```
select distinct name from student;
```

```
select count(*) from student;

select * from student where fathername is null;

select * from student where fathername is not null;

select * from student where studentid <> 5;

select * from student where studentid < 5;

select * from student where studentid > 5;

select * from student where studentid >= 5;

select * from student where studentid <= 5;

select * from student where studentid in (1,4,7,8,10);

select * from student where studentid not in (1,2,3);

select * from student where email_address like '%sher';

select * from student where email_address like '%er%';

select * from student where email_address like '%gmail.com';

select * from student where email_address like '%badnam%.com';

select * from student where studentid between 5 and 8;

select * from student order by name;

select * from student order by name asc;

select * from student order by name desc;

select * from student where not studentid = 2;

SET SQL_SAFE_UPDATES=0;
```

### Delete 

```
delete from student where Name = 'Shera';

delete from student;

drop table student;

drop database wecodeacademy;

select min(studentid) from student;

select max(name) from student;

select count(*) from student;

select count(studentid) from student;

select count(*) from student where fathername = 'Kalam Khan';

select avg(studentid) from student where fathername = 'Kalam Khan';

select sum(studentid) from student;
```
### UPDATE 
```
update student set name = 'Vajid' where studentid=2;

update student set name = 'Vajid';

update student set name = 'Vajid', email_address = 'vajid@gmail.com' where studentid  = 1;
```
 ### LIMIT
 ```
select * from student limit 2;

select * from student where email_address like '_ajid%';

select * from student where city like '__rta';
```
### GROUP BY
```
select * from student group by name;

select count(*), name from student group by name;

select count(*), fathername from student group by fathername;

select count(*), fathername, mobile from student group by fathername, mobile;
```

### COUNT ,MAX AND ALTER
```
select *  from student group by name having count(name) >= 3;

select *  from student having max(studentid) > 3;  --notes

alter table student add course varchar(255) not null;

alter table student drop column fathername;

ALTER table student Add column pincode integer AFTER name;

ALTER TABLE student MODIFY COLUMN pincode varchar(255);

ALTER TABLE student RENAME COLUMN pincode TO zipcode;
```

Error Code: 1055. Expression #1 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'school.student.student_id' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql_mode=only_full_group_by
 
 ###  nhi chali
 select * from student group by 
select *  from student group by name having count(name) >= 3;
select name from student having max(student_id)>3;


create table student (
`stuId` integer primary key auto_increment not null,
`stuName` varchar(30) not null,
`fName` varchar(30),
`course` varchar(20) not null,
`email` varchar(40) not null,
`mobile` bigint,
`address` varchar(55) not null
);

create table fees (
 `feeid` integer UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT, 
 `amount` bigint,
 `month` varchar(255),
 `stuId` integer
);


    
