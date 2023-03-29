### SQL 

How to create the student table in MySQL?
```
create table student (
`stuId` integer primary key auto_increment not null,
`stuName` varchar(30) not null,
`fName` varchar(30),
`course` varchar(20) not null,
`email` varchar(40) not null,
`mobile` bigint,
`address` varchar(55) not null
);
```

How to create the fees table in MySQL?

```
create table fees (
 `feeid` integer UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT, 
 `amount` bigint,
 `month` varchar(255),
 `stuId` integer
);
```

How to insert a new fee record into the fees table for a particular student?
```
By studentid field 

insert into fees ( amount ,month, stuId)
values(  3000  ,'feb' , 4);
```

How to update a student record in the student table?
```
update student  set  fName ='etc'  where stuId = 4; 
```
How to update a fee record in the fees table?
```
update fees  set  amount = 4000  where stuId = 4; 
```

How to select all the records from the fees table?
``` 
select * from fees;
```

How to select a particular student record from the student table?
```

select * form student where studentId = 1;
```
How to select all the fee records for a particular student from the fees table?
```
select * from fee where studentId = 1;
```

How to get the total number of students in the student table?
```
select count(*) from student;
```

How to get the sum of all the fees paid by a particular student?
```
select sum(amount) from fees;
```
How to get the average fee paid by all the students?
```
select avg(amount) from fees;
```
How to get the student record with the highest mobile number in the student table?
```
select max(mobile) from student;
```
How to get the fee record with the highest fee amount in the fees table?
```
select max(amount) from fees;
```

How to get the list of all students who live in a city?
```
select city from student;
```

How to get the list of all students who have paid fees for the month of 'February'?
```
select * from fees where month = "feb" and amount = is not null;
```
How to get the list of all cities along with the count of students living in each city?
```
select address,count(stuId) from student group by address;
```

How to get the list of all cities along with the count of students living in each city, where the count is greater than 1?
```
select address from student group by stuId having count(stuId)>=1;
```
How to get the list of all students sorted by their names in ascending order?
```
select * from student order by stuName;
```
How to get the list of all students sorted by their mobile numbers in descending order? 
```
select * from student order by mobile desc;

```
How to get the list of all fees records sorted by the fee amount in descending order?
```
select * from fees order by amount desc;
```

How to get the list of all fees records sorted by the fee amount in descending order, for a particular student?
```
select * from fees where stuId = 2 order by amount desc;
```
### student
    pincode
    city
    state
    country
    mode:  online/offlie
    minor: true/false

    @@@
    student 10 records
fee table 20 records
result 15 records

### result
    id
    totalmarks 100
    obtainedmarks 80
    subject nodejs
    testdate date
    studentid foreign key


### questions 

1. khan

select * from student where name like '%khan%';

2. where studentid between 5 and 10

select * from student where stuId between 5 and 10;

3. Rename fathername column to mothername

ALTER TABLE student RENAME COLUMN fName TO mName;

4. kaunse month me sbse jyada fees aayi hai

 select month, sum(amount) as total from fees group by month order by total desc limit 1;

5. kaunse month me sbse kam fees aayi hai

select month, sum(amount) as total from fees group by month order by total asc limit 1;

6. sbse jyada fees kis student ne di hai

select stuId, sum(amount) as total from fees group by stuId order by total desc limit 1;

 CHECK => select * from student where stuId = 10;

7. sbse kam fees kis student ne di hai

select stuID, sum(amount) as total from fees group by stuId order by total asc limit 1;

select * from student where stuId = 7;

8. aise kaunse student hai jinhone ek b bar fee ni di hai

select distinct stuId from fees;

select * from student where stuId not in (3, 4, 7);

9. aise kaunse students hai jinka mobile and fathername ni hai db me

select * from student where mobile is null and fName is null;

10. vo sare students ka record delete krdo jinhone koi fees ni di hai

select distinct stuId from fees;

delete from student where studentid not in (15,17,18);
