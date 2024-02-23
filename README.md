# 1. Sql Server Introduction
### What is database?
jaha aap info store kar sakte aur later on retreive bhi kar sakte. Sath sath manupulate bhi kar sakte.
### What is RDBMS?
multiple object mein relationship taiyyar kar sakte, aur data aap relationship ke sath access kar sakte.  
- SQl Server is RDBMS
- Sql server ki apni language hai i.e T-SQL

![Alt text](image.png)
![Alt text](image-1.png)
SQL Server Enterprize 
- large volume ke data ko handle karne ke liye use hota hia.  
- advanced analytics aur m/c learning ke liye use kiya jata hia

Sql server devloper 
 - aap production mein use nhi kar sakte

 ![Alt text](image-2.png)

 Database Engine
  - db object ko store & execute bhi kar sakte ho
  - Transaction mgm ye bhi kaam hai iska

  ![Alt text](image-3.png)

  Sql Server VSs writer 
   - db ko restore karna aur backup lena
# 2. Create alter and drop db
![Alt text](image-4.png)
Database 
 - collection of data
 - structure form (table format mein)
 - table consist of row and column
 - db structure help karta hia info access karne ke liye 
 - aur data manipulate karne ke liye bhi
![Alt text](image-5.png)
![Alt text](image-6.png)

System db
 - na drop kiya ja sakta hia na rename

 ![Alt text](image-7.png)
 ### Create db
 ![Alt text](image-8.png)
 ### Drop db
 ![Alt text](image-9.png)
 ### Rename db
 ![Alt text](image-10.png)
 ### More specific rename command
 ![Alt text](image-11.png)
 ### Microsoft UI ke via kaise db create kare
 ![Alt text](image-12.png)
![Alt text](image-14.png)
 ![Alt text](image-13.png)
 ![Alt text](image-15.png)
 ![Alt text](image-16.png)
### U can add filegroup
![Alt text](image-17.png)
![Alt text](image-18.png)
### For delete or rename
![Alt text](image-19.png)  
### delete ke liye close existing connection.
![Alt text](image-20.png)
# 3. Creating table in Sql
![Alt text](image-21.png)
![Alt text](image-22.png)
- Ek db ke andar aap multiple table rakh sakte ho
- basharte Table  name unique ho 
- table format consist of row and column
- Column define karte waqt aap datatype defined karte ho.. ki kis type ka data save honga.
![Alt text](image-23.png)
#### char(n)  
 - char ki length apne define kari hai 10 charchter  & aapki value hai 5 character tab bhi memory mein 10 char lenga.
 #### varchar(n)
- variable character, apki length hai 100 and value hai 20 so sql server 80 spaces ko memory se remove kar denga.
#### Nchar aur char mein space diff hai 4000 & 8000 ka, reason is 1 byte / 2byte
- aap unicode character ie Non-ackii character like china/russsia language aap store kar skate ho
### bit
- boolean value ko store karene ke liye
![Alt text](image-24.png)
RDBMS mein data table ke form mein store hota hai. 
which furthur bifurcate into row and column.  

![Alt text](image-25.png)
### Show database & create db and use it
![Alt text](image-26.png)
### Create table
![Alt text](image-27.png)
![Alt text](image-28.png)
![Alt text](image-29.png)
### Table name must be unique. 1 db 1 unique table name.
### If you want to use reserve word as column name
![Alt text](image-30.png)
### Solution
![Alt text](image-31.png)
### Select statement
![Alt text](image-32.png)
### DROP TABLE COMMAND
![Alt text](image-33.png)
Physically data samet table remove ho gya apke db se.
### Error's
![Alt text](image-34.png)
### Creating table
![Alt text](image-35.png)
### Select query
![Alt text](image-36.png)
### Alter the table
![Alt text](image-37.png)
### Modify the table
![Alt text](image-38.png)
#### Abhi city ki length hai 10
![Alt text](image-39.png)
### DROP COLUMN
![Alt text](image-41.png)
## AAP UI ke thorugh bhi table create kar skate ho
![Alt text](image-42.png)
![Alt text](image-43.png)
![Alt text](image-44.png)
### Ab apko column ko edit karna hia via UI
![Alt text](image-45.png)
#### dob ko hatana hia
![Alt text](image-46.png)
after save it
# 4. Sql Constraint
constraint 
- something that limits you
- अवरोधकारी तत्‍व; प्रतिबंध; सीमित करने वाले नियंत्रण
#### Sql Constraint ye rules hote hai jo aapke data ko validate karte hai
- eg. har data collect karke joh table create karte hai to uska ek purpose hota hia..  
yadi usme 8th 9th standard ka data raha to galat ho javenga..  
 For this you need to create a rule such that your system only accept 12th standard data  
 This is called constraint
 - employee table mein wohi employee ka data chaiye jiske age 40 se kam ho.

 ![Alt text](image-47.png) 
 ![Alt text](image-48.png)
 ### Remember Not Null ye space nahi hai.. dono diff hote hai
 ### Primary key aur unique key ka diff 
 - primary key mein null value allow nhi hoti 
 - unique key mein 1 null value allow
 ### Foreign key-
  - 2 table mein relationship create karte hai
### Check
- check mein aap rule bana sakte ho(emp > 40 ) ye rule bana sakte ho
### Defualt 
- mein aap initial value set kar sakte hai kisi bhi column ke liye.(column aapka not null hai)
### Table level
- hum multiple column par constraint create kar sakte hai
```sql
use MyDatabase;

-- 1) Not NULL
--   Ensures column cannot have null values

Create Table Test
(
	RollNo INT NOT NULL,
	NAme VARCHAR(100),
	Class Varchar(10)
)

-- janbhujkar roll no skip kiya
insert into Test(NAme,Class) Values ('King','12');

```
### ***Error***
```sql
Cannot insert the value NULL into column 'RollNo', table 'MyDatabase.dbo.Test'; column does not allow nulls. INSERT fails.
The statement has been terminated.
```
### Proper query
```sql
insert into Test(RollNo,NAme,Class) Values (1,'King','12');
```
### Yaha table structure mein dikh raha hia ki Rollno not null hai.
![Alt text](image-50.png)
### Aap null jaha allow hai column skip kar sakte.
```sql
insert into Test(RollNo,Class) Values (1,'12');
Output:
No issue
```
## Same thing you achieve via UI
![Alt text](image-51.png)
![Alt text](image-52.png)
## Aisa table create karte jisme koyi constraint nhi
```sql
Create Table Test2
(
	RollNo INT ,
	NAme VARCHAR(100),
	Class Varchar(10)
)

insert into Test2(Name,Class) Values ('Adit','12');

select * from Test2;

Output:
NULL	Adit	12
```
### Ab yadi hume Test2 table ke RollNo col ko Not Null karna hai, 
 - table to create hue hai
 - usme 1 record bhi insert ho chuki hai
 ```sql
 insert into Test2(Name,Class) Values ('Adit','12');

select * from Test2;

alter table Test2
   alter column RollNo INT NOT NULL;
```
### Error
```sql
Cannot insert the value NULL into column 'RollNo', table 'MyDatabase.dbo.Test2'; column does not allow nulls. UPDATE fails.
```
#### Apne pehle hi record insert kiya hai joh null value le raha hia 
#### aur app abhi column ko modify kar rahe ho not null so problem denga
### Solution 1st data ko clear karo then query chalao
```sql
delete from Test2;

alter table Test2
   alter column RollNo INT NOT NULL;
```
### Unique constraint
```sql
-- Unique
--  All the values in the column must be unique.

Create Table TestUnique
(
	rollNo INT UNIQUE,
	name VARCHAR(100),
	class VARCHAR(10)
)

insert into TestUnique(rollNo,name,class) 
						values(1,'King',12);

select * from TestUnique;

Output:
1	King	12
```
### Ab yadi hum fhirse same insert query chalate hai tab.
```sql
insert into TestUnique(rollNo,name,class) 
						values(1,'King',12);
```
#### Error
```sql
Violation of UNIQUE KEY constraint 'UQ__TestUniq__FABBB772AE9DE7E1'. Cannot insert duplicate key in object 'dbo.TestUnique'. The duplicate key value is (1).
```
![Alt text](image-53.png)
### Insert more values
```sql
insert into TestUnique(rollNo,name,class) 
						values(2,'King',12);

select * from TestUnique;
Output:
1	King	12
2	King	12

Name & class ye column unique nhi hai so duplicate value bhi ja sakta + null bhi.
```
![Alt text](image-54.png)
### Apka table create ho chuka aur aapko unique constraint add karni hai-ya constrain name change karna hia
```sql
-- alter(K) table(K) tableName
          -- add(K) constraint(K) constraintName(USER_DEfined)  Unique(K)(columnName) 

alter table TestUnique
       add constraint UniqueRollNO UNIQUE(rollNo);
```
![Alt text](image-55.png)
## Primary Key
```sql
-- Primary Key
     -- A primary key is the field which can uniquely identify each row in a table
	 -- Only 1 primary key is allwoed in a table.
	 -- You may have multiple unique key in a table.
	 -- Primary key does not allow any null value but unique key can allow NULL value.


-- Multiple primary key
create table DemoPK
(
	rollNo int Primary key,
	mobileNo int primary key,
	city varchar(100)
)
Error:
Cannot add multiple PRIMARY KEY constraints to table 'DemoPK'.
-----------------------------------------
-- Multiple unique key
create table DemoPK
(
	rollNo int Unique,
	mobileNo int Unique,
	city varchar(100)
)
Output:
Success table created.
------------------------------------
drop table DemoPK;
-- About null value
create table DemoPK
(
	rollNo int Primary key,
	mobileNo int Unique,
	city varchar(100)
)

-- Yaha humne rollNo jo primary key hai usse nhi liya..
-- yadi aap skip karte hai kisi col ko so null value usme dali jati hai
--     Yaha aisa kuch nahi
insert into DemoPK(mobileNo,city) 
                  values(44334,'LONDON');
Error:
Cannot insert the value NULL into column 'rollNo', table 'MyDatabase.dbo.DemoPK'; column does not allow nulls. INSERT fails.
---------------------------------------------------
-- Proper query
insert into DemoPK(rollno,mobileNo,city) 
                  values(1,44334,'LONDON');
Output:
Success record is inserted.
-------------------------------------------
-- regarding null value for unique key
insert into DemoPK(rollno,city) 
                  values(2,'New York');

select * from DemoPK;
Output:
1	44334	LONDON
2	NULL	New York

Observation:
Null is allowed in unique key but only once.

-- inserting again null value for unique key
insert into DemoPK(rollno,city) 
                  values(3,'Japan');
Error:
Violation of UNIQUE KEY constraint 'UQ__DemoPK__4D7970A8C39373BE'. Cannot insert duplicate key in object 'dbo.DemoPK'. 
The duplicate key value is (<NULL>).
----------------------------------------------

-- inserting non null value for unique key

insert into DemoPK(rollno,mobileNo,city) 
                  values(4,777,'Japan');

select * from DemoPK;

Output:
1	44334	LONDON
2	NULL	New York
4	777	     Japan
--------------------------------
-- inserting same non null value for unique key

insert into DemoPK(rollno,mobileNo,city) 
                  values(5,777,'Japan');

Error:
Violation of UNIQUE KEY constraint 'UQ__DemoPK__4D7970A8C39373BE'. Cannot insert duplicate key in object 'dbo.DemoPK'.
 The duplicate key value is (777).

Observation:
Unique contian unique elements only.
-----------------------------------
```
### Via UI- check in Design Mode
![Alt text](image-56.png)
#### jab bhi aap table create karte hai UI se to yaha se add/remove kar sakte hai i.e PK
![Alt text](image-57.png)
![Alt text](image-58.png)
## Check Constraint
- We can specify a condition for a field,   
   which should be satisfied at the time of entering value for     
      particualr field.
```sql
-- Check Constraint
/*
We can specify a condition for a field, 
   which should be satisfied at the time of entering value for 
      particualr field.
*/
use MyDatabase;

-- Koyi bhi employee ki age 40 se jyada nhi honi chaiye.

create table DemoCheck
(
	rollNo int primary key,
	age int NOT NULL CHECK(age <= 40)
)

-- insert data
insert into DemoCheck(rollNo,age) 
                values(1,45);

```
 ### Error
 ```sql
 The INSERT statement conflicted with the CHECK constraint "CK__DemoCheck__age__59063A47". The conflict occurred in database "MyDatabase", table "dbo.DemoCheck", column 'age'.
 ```
 ```sql
 -- proper query 
insert into DemoCheck(rollNo,age) 
                values(1,35);
Ouput:
1 row affected

-- check it
select * from DemoCheck;
1	35

 ```
## Default constraint
- This constraint is used to define default value for the field.
```sql
-- Default Constraint
-- This constraint is used to define default value for the field.

use MyDatabase;

create table DemoDefault
(
  rollNo int Primary Key,
  age int NOT NULL Default 22,
  recordDate DateTime  Default GetDate()
)

insert into  DemoDefault(rollNo)
                 values (1);

select * from DemoDefault;
/*
Yaha aapne keval rollNo mention kiya hai baki ka    data toh diya bhi nahi.   Usne sabki default value utha li.
Output:
 1	22	2024-02-20 08:17:07.863
*/

-- par yadi aap value de rahe hai to default value ko skip kar denga.
insert into  DemoDefault(rollNo,age,recordDate)
                 values (2,34,'2020-02-20');

-- check
select * from DemoDefault;
/*
Output:
1	22	2024-02-20 08:17:07.863
2	34	2020-02-20 00:00:00.000
*/

```
![Alt text](image-59.png)
## Foreign key Constraint
- 2 table mein relationship create karta hai.

![Alt text](image-60.png)
### Advantage of Foreign key
- Aap manmaana koyi bhi rollNo StudentMarksFK mein enter nahi kar sakte, Yadi wo uske Master table ie StudentPK mein exist nahi karta ho to.
- Aap StudentPk table i.e master table se koyi bhi rollNo randomly delete nahi kar sakte, yadi uska data child table i.e StudentMarksFK mein existe karta ho.
- Aapko pehle child table se data delete karna honga then master table se.
- Ye concept se hamare data mein accuracy aa gayi. Jo data master table mein hai uske traces i.e data child table mein mil javenge..

```sql
-- Foreign key Constraint
/*
Foreign Key is a field in a table which uniquely identified each row in another table.
That is, this field points to primary key of another table.
This usually creates a kind of link between the tables.
Data type of both key must be same.
*/

use MyDatabase;

Create Table StudentPk
(
  RollNo Int Primary Key
)

Create Table StudentMarksFK
(
	RollNo Int,
	Term Varchar(100),
	Science Int,
	Math Int,
	Eng Int,
	Foreign Key (RollNo) References StudentPK(RollNo)
)

-- 2 tables are created

-- Sabse pehle hum StudentMarksFK Table mein data insert karte hai.
-- Rule kya bolta
--   yadi aapki primary key exist nahi karti StudentPK table mein
--  to aap StudentMarksFK table mein data insert nhi kar sakte.

Insert Into StudentMarksFK(RollNo,Term,Science,Math,Eng)
            Values(1,'Final',55,78,89);

/*
The INSERT statement conflicted with the FOREIGN KEY constraint 
"FK__StudentMa__RollN__60A75C0F". The conflict occurred in database 
"MyDatabase", table "dbo.StudentPk", column 'RollNo'.
*/
```
#### sabse pehle Master table mein data enter karna honga.
```sql

Insert Into StudentPk(RollNo)
               Values(1);
Insert Into StudentMarksFK(RollNo,Term,Science,Math,Eng)
            Values(1,'Final',55,78,89);

--Check data for both
Select * from StudentPk;
-- 1
Select * from StudentMarksFK;
-- 1	Final	55	78	89

-- again inserting data jo master table mein nhi hai..
Insert Into StudentMarksFK(RollNo,Term,Science,Math,Eng)
            Values(2,'Half Yearly',55,78,89);
/*
Error:
The INSERT statement conflicted with the FOREIGN KEY constraint 
"FK__StudentMa__RollN__60A75C0F". The conflict occurred in database "MyDatabase",
table "dbo.StudentPk", column 'RollNo'
*/

-- Correct query
Insert Into StudentPk(RollNo)
               Values(2);

Insert Into StudentMarksFK(RollNo,Term,Science,Math,Eng)
            Values(2,'Half Yearly',55,78,89);
--Check data for both
Select * from StudentPk;
-- 1
-- 2
Select * from StudentMarksFK;
-- 1	Final	55	78	89
-- 2	Half Yearly	55	78	89
```
```sql
-- let say hum StudenPK se data delete karte hai.
delete from StudentPk where RollNo=1;
/*
Error:
The DELETE statement conflicted with the REFERENCE constraint 
"FK__StudentMa__RollN__60A75C0F". The conflict occurred in database 
"MyDatabase", table "dbo.StudentMarksFK", column 'RollNo'.

Mane=
RollNo ka data aapka child table mein bhi hai
jab tak waha se delete nhi honga.. hum master table se delete nhi
kar sakte.
*/
-- Correct query
delete from StudentMarksFK where RollNo=1;

--Check data for both
Select * from StudentPk;
-- 1
-- 2
Select * from StudentMarksFK;
-- 2	Half Yearly	55	78	89

-- Ab aap aasani se master table ka data delete kar sakte.
-- kyuki child class mein uska fk trace exist nhi karta.
delete from StudentPk where RollNo=1;

--Check data for both
Select * from StudentMarksFK;
-- 2	Half Yearly	55	78	89

Select * from StudentPk;
-- 2
```
## Table level Constraint.
```sql
-- Table level Constraint
-- Constraint can be specified for the groups of columns as a part of table.

use MyDatabase;

-- hume rollNo aur moblie column ki sahayata se table ko unique banana hai

Create Table DemoTableLevel
(
  RollNo Int,
  MobileNo Int,
  City Varchar(100),
  Constraint Roll_Mobile_Unique Unique(RollNo,MobileNo)
)

-- ab apke table ka RollNo aur mobileNo ka combination hamesha unique honga

Insert into DemoTableLevel(RollNo,MobileNo,City)
                 Values(1,222,'London');

-- Check data
Select * from DemoTableLevel;
-- 1	222	London

-- ab yadi phir se same record insert karu to
Insert into DemoTableLevel(RollNo,MobileNo,City)
                 Values(1,222,'London');
/*Error
Violation of UNIQUE KEY constraint 'Roll_Mobile_Unique'. Cannot insert duplicate 
key in object 'dbo.DemoTableLevel'. The duplicate key value is (1, 222).

Mane:
Jo combination ki value hai wo duplicate hai.
*/

-- Another query
Insert into DemoTableLevel(RollNo,MobileNo,City)
                 Values(2,222,'London');

-- Check data
Select * from DemoTableLevel;
-- 1	222	London
-- 2	222	London

--Observation:
--Roll No change kiya but mobile no same hai.. chal javenga.
--Combination must be unique

--Another query
Insert into DemoTableLevel(RollNo,MobileNo,City)
                 Values(2,333,'London');

-- Check data
Select * from DemoTableLevel;
-- 1	222	London
-- 2	222	London
-- 2	333	London

--Observation:
--Combination is unique.
```
# 5. Sql Identity column
![Alt text](image-61.png)
![Alt text](image-62.png)
```sql
use MyDatabase;

-- How to create Identity column

Create Table Test1
(
-- Primary key= unique and not null
	ID Int Primary Key,
	FNAME Varchar(100)
)

--Insert Data
Insert into Test1 Values(1,'John');

-- Check
Select * from Test1;
--1	John

--Problem kya hai
-- 1)Humko insert karte waqt last Unique ID kya tha wo yaad rakhna padenga
--    Hume Tile add karna hai humne aise query likhe.
Insert into Test1 Values(1,'Tile');
/*
Error:
Violation of PRIMARY KEY constraint 'PK__Test1__3214EC2797C07F83'.
Cannot insert duplicate key in object 'dbo.Test1'. The duplicate key value is (1).
*/

-- 2) Problem
--     yadi humne random number likh diya
Insert into Test1 Values(19,'Tile');
-- Check
Select * from Test1;
--1	    John
--19	Tile
--     To yaha data to insert ho gya, but unique value sequence mein nhi hai.
--  So mujko yadi data ko sequentially enter karna hia.. To last value yadd
--     rakhna honga.

Drop Table Test1;
```
### Solution is go for Identity column
#### via UI
![Alt text](image-63.png)
![Alt text](image-64.png)
#### So aap increment aur seed yaha se bhi specify kar sakte hai.
```sql
-- Create via DDL statement
Create Table Test1
(
--Identity(seed value,Increment)
	ID Int Identity(1,1),
	FNAME Varchar(100)
)

-- Rule no 1.
--   Identity column ke andar value aap explicitly insert nahi kar sakte
--    If i try this command
Insert into Test1 Values(1,'John');
/*
Error:
An explicit value for the identity column in table 'Test1' can only be specified 
when a column list is used and IDENTITY_INSERT is ON.

Identity column ke andar aap value explicitly insert nahi kar sakte
kyuki  isko system generate karta hai.
*/

-- so our correct query is
Insert into Test1 Values('John');
Insert into Test1 Values('King');
Insert into Test1 Values('Miler');

-- Check
Select * from Test1;
--1	    John
--2  	King
--3	    Miler

-- Observation
--  Data is generated in sequence 
--    aur id ki value bhi unique hai
```
### Suppose i delete the data
```sql
Delete Test1 where id=2;

-- Check
Select * from Test1;
--1	    John
--3	    Miler

-- Ab yadi mein record insert karta hu
Insert into Test1 Values('King');

-- Check
Select * from Test1;
--1	    John
--4	    King
--3	    Miler

-- Observation:
--  Ab ki baar King to add hua but id =4 par

-- Yadi hum 2 par insert karna chahe to
Insert into Test1(ID,FNAME) Values(2,'King');

-- Error:
--   Cannot insert explicit value for identity column in table 'Test1'
     --  when IDENTITY_INSERT is set to OFF.\
	 --       IDENTITY_INSERT abhi off hai boss.

-- Id  Insert karna hi hai

-- Set IDENTITY_INSERT Table_Name ON
Set IDENTITY_INSERT Test1 ON

Insert into Test1(ID,FNAME) Values(2,'King');

-- Check
Select * from Test1;
--1	    John
--4	    King
--3	    Miler
--2		King

-- Is tarh se Identity column ke andar value ko Explicitly insert kar sakte.

-- Abhi hum yadi query chalaye.
Insert into Test1 Values('Aditya');
/*
Error:
Explicit value must be specified for identity column in table 'Test1' either when 
IDENTITY_INSERT is set to ON or when a replication user is inserting into a 
    NOT FOR REPLICATION identity column.

Why?
kyuki IDENTITY_INSERT is set to ON hai.
*/

-- Make it off
Set IDENTITY_INSERT Test1 OFF

Insert into Test1 Values('Aditya');


-- Check
Select * from Test1;
--1	    John
--4	    King
--3	    Miler
--2		King
--5		Aditya
```
### How to reset Identity column
```sql
-- How to reset Identity column
   -- Yane starting value ko reset kaise kare.

-- Check
Select * from Test1;
--1	    John
--4	    King
--3	    Miler
--2		King
--5		Aditya

-- Ye hamara existing record hai 
    -- ab hume iske aage ka next record 10 se insert karna hia

 -- ab yadi hum query chalaye
 Insert into Test1 Values('Abhi');

 -- Check
Select * from Test1;
--1	    John
--4	    King
--3	    Miler
--2		King
--5		Aditya
--6		Abhi

 -- Observation
      -- next sequence row mein insert ho raha hia.

-- hum chahte hai iske baad direct 10th row se insert ho
DBCC CheckIdent(Test1,RESEED,10);

 Insert into Test1 Values('King-2');
  Insert into Test1 Values('King-3');

-- Check
Select * from Test1;
--1	    John
--4	    King
--3	    Miler
--2		King
--5		Aditya
--6		Abhi
--11	King-2
--12	King-3

-- Observation:
   -- Aap kisi bhi state se Identity reset kar sakte.
```
### How to get last inserted identity value
![Alt text](image-65.png)
- ye ek system function hai jo last identity ko retrun karta hia.
- current session mein kayi sare scope hai, sabme procedure hai. Usme se kisi mein latest identity update hue hai. Ye function wo value return karenga.
```sql
/*
	How to get last inserted identity value
	 - @@identity
	 - Scope_identy
	 - Idnt_current
*/

Drop Table test1;
Drop Table test2;
Drop Table test3;

--Hum 3 naye table create karte hai
Create Table Test1
(
	ID Int Identity(1,1),
	FNAME Varchar(100)
)
Create Table Test2
(
	ID Int Identity(200,1),
	FNAME Varchar(100)
)
Create Table Test3
(
	ID Int Identity(300,1),
	FNAME Varchar(100)
)

-- ab data insert karte hai
Insert Into Test1 Values('T1');
Insert Into Test2 Values('T2');
Insert Into Test3 Values('T3');

Select @@IDENTITY 
-- 300

-- Ye latest value apki insert hue hai Test3 table mein so it return that..

-- ab yadi hum iska sequence change karde
Insert Into Test1 Values('T1');
Insert Into Test3 Values('T3')
Insert Into Test2 Values('T2');

Select @@IDENTITY 
-- 201

-- Observation :  Ab ye table 2 ki identity value provide kar raha hia.


Insert Into Test3 Values('T3')
Insert Into Test2 Values('T2');
Insert Into Test1 Values('T1');

Select @@IDENTITY 
-- 4

-- Observatation: table 1 ki latest identity value provide kar riya hai.
```
### Some more things.
```sql
--Create Procedure

Create Proc p1
As
Begin
    Insert Into Test1 Values('T1');
End

Create Proc p2
As
Begin
    Insert Into Test2 Values('T2');
End

-- Procedure 1 ka scope diff hai than procedure 2 
     -- so hum Procedure 1 mein ki value proc 2 mein use nhi kar sakte.

-- Now Execute Procedures.
EXEC p1;
EXEC p2;

Select @@IDENTITY;
-- 203

-- Yaha Proc2 mein table2 i.e Test2 ka latest identity value diya.

-- If i change the execution sequence
EXEC p2;
EXEC p1;

Select @@IDENTITY;
-- 6

-- kisi bhi scope mein ho yaha fark nahi pad raha hai.
```
### Par ha ye current session ke liye hi honga. If you open another window then that is another session.
![Alt text](image-66.png)
## Scope_identity
![Alt text](image-67.png)
```sql
Delete from Test1;
Delete from Test2;

-- abhi data check kiya sara blank hai
Select * from Test1;
Select * from Test2;

-- procedure create kari
Create Proc p1
As
Begin
    Insert Into Test1 Values('T1');
End

Create Proc p2
As
Begin
    Insert Into Test2 Values('T2');
End

-- ab data insert karte aur sath hi procedure execute kartea

-- ye insert kiya hua value abhi default scope mein hai.
Insert Into Test1 Values('T1');
EXEC p2;
EXEC p1;

-- check data
Select * from Test1;
--7		T1
--8		T1

Select * from Test2;
--205	 T2

Select Scope_Identity();
-- 7
    -- ye default scope ki identity de raha hai.
	   -- current scope mein jo last value generate hue hai usko ye fetch karta.


-- Yaha aap kis sequence mein data insert kar rahe hai ye matter nhi karta.
EXEC p2;
Insert Into Test1 Values('T1');
EXEC p1;

-- check data
Select * from Test1;
--7		T1
--8		T1
--9		T1
--10	T1

Select * from Test2;
--205	 T2
--206	T2

Select SCOPE_IDENTITY();
-- 9
     -- default scope ne jo value enter hue regardless of sequence of execution wo aayi.
```
### Ident_current
![Alt text](image-68.png)
- koyi bhi connection ho, aur koyi bhi scope iske liye matter nhi karta.
- jo table name aapne supply kiya hia.. uski last identity value ko ye fetch karke de deta.
```sql
EXEC p2;
Insert Into Test1 Values('T1');
EXEC p1;

-- check data
Select * from Test1;
--7		T1
--8		T1
--9		T1
--10	T1
--11	T1
--12	T1

Select * from Test2;
--205	T2
--206	T2
--207	T2

Select IDENT_CURRENT('Test1');
-- 12
  -- isme aapka koyi bhi sequence ho, ya koyi connection ho
      -- koyi matter nahi karta
	   -- ye latest identity for particular table provide karta hai.

	   
Select IDENT_CURRENT('Test2');
--207
```
# 6. Super Key, Candidate key,Composite, Unique etc
![Alt text](image-69.png)
### Super key
- attribute kahe to column in a table
- aise single / multiple / combination of attributes mila kar ke yadi kisi row ko hum uniquely identifies kar sake to i.e super key 

![Alt text](image-70.png)
- hum id se uniquely identify kar sakte row ko, so this is super key
- hum id aur name ko combine kar le, so super key ban javenga.
- id + gender; id + city; yane hum single attribute ya multiple attribute combine kar ke yadi row ko uniquely identify kar sake to i.e super  key.
### Candidate key
- ye table ke andar single ho sakti ya multiple
- koyi bhi attribute(field or column name) candidate key ho sakta hia
- make sure column ke andar value unique ho

![Alt text](image-71.png)
- ye table mein bcaz of duplicacy koyi candidate key nahi hai.

![Alt text](image-72.png)
### Primary key
- unique value ko maintain karta hia column ke andar
- null value are not allowed
- 1 primary key for 1 entire table

![Alt text](image-73.png)
- aap usko primary bana sakte jo unique ho entire table mein aur usme null na ho
- yaha empid primary key liya
- so remaining unique key is alternate candidate keys or alternate key kehlati.
### Unique key
- unique value ko maintain karta
- ek table mein multiple unique key ho sakta hai
- 1 null value is allowed in a column

![Alt text](image-74.png)
- jo green color mein hai wo sare unique key hai
### Composite key
- kabhi kbahi table ke andar composite key ki jarurat padti hai
- kisi table ke data ko uniquely identify karne ke liye composite key hota hai
- contians 2 or more column jo uniquely identify kare row ko

![Alt text](image-75.png)
- ksis bhi teacher ki id aur qualification id combinely duplicate enter nahi hona chaiye.
### Foreign key
- 2 ya 2 se jayda table mein relationship create karta hai.
- master-details or parent- child relationship kehte hai.
- foreign key ka purpose data integrity ko maintain karne ke liye hota hai.

![Alt text](image-76.png)
- dono table independent hai
- ab mujhe query fire karni hai(dono table se data lekar anna hai- but yaha koyi relationship nahi hia.)

![Alt text](image-77.png)
- yaha relationship create hua hai
- foreign key apka duplicate ho sakta hia
- primary key ek hi honga entire table ke liye.
# 7. Temprary table in sql server.
- ye table aap create karte hai, fhir uspar aap processing karte hai; tatpashat aapka task khatam ho jata hai
- so aap connection ko close karte hai, aur aapke sare temprary table drop ho jate hai.

![Alt text](image-78.png)
![Alt text](image-79.png)
#### Local Table
- Yadi particular session mein table create kiye. toh usi session mein appko access ho sakti hai wo table.
- ek baar session close then table drop automatically.
- use # to create table.
#### Global table
- ek baar table create hue kisi bhi session mein, aap multiple session mein bhi table acess kar sakte 
- read dig

![Alt text](image-80.png)
- faster than permanant table.
- agar apke pass kisi table ke rights nahi hai. So aap uska temprary table create karke, usko manipulate kar sakte.
- aap chahte ho ki apka data kisi ko visible na ho us case mein bhi aap temprary table create kar sakte.
```sql
use MyDatabase;

/*
	Local Temprary table

	For creating temp use # as prefix
	It is created in tempDb

	2 tarike se create kar sakte aap local temp table
	  - Select Into and
	  - create table statements
*/

Create table Student_Marks
(
	RollNo Int Identity(1,1),
	Science Int,
	Math Int,
	Eng Int
)

Insert into Student_Marks Values(34,78,54);
Insert into Student_Marks Values(78,43,87);
Insert into Student_Marks Values(45,32,78);
Insert into Student_Marks Values(36,78,32);
Insert into Student_Marks Values(12,22,67);
Insert into Student_Marks Values(21,65,43);
Insert into Student_Marks Values(34,78,54);
Insert into Student_Marks Values(89,78,54);
Insert into Student_Marks Values(76,78,54);
Insert into Student_Marks Values(22,56,54);

select * from Student_Marks;

-- Ab suppose hume ek temprary table create karni hai iss table se

-- select * into  tempTableName from tableName
     -- apne * diya for all column
	  -- particular column bhi provide kar sakte.
Select * Into #localTemp from Student_Marks;
```
### Humko localTemp temprary table kaha dikhenga?
![Alt text](image-81.png)
### furthur more..
```sql
-- Ab yadi hum ispar select statement chalate hai 
select * from #localTemp;
/*
Output:
RNo Sc  Mat Eng
1	34	78	54
2	78	43	87
3	45	32	78
4	36	78	32
5	12	22	67
6	21	65	43
7	34	78	54
8	89	78	54
9	76	78	54
10	22	56	54
*/

-- Observation: Temprary table mein sara data aa gya 
```
### Ab yadi ek aur session create karke hum ye same command chalate hai tab
![Alt text](image-82.png)
#### Remember : aapka local temprary object wahi mane ussi session mein access honga jaha create hua hai. dusre session mein nhi
#### Ab yadi hum current session mein- jaha localtemp ka object create hai waha se data delete karta hu.
```sql
delete from #localTemp where RollNo=1;

--check
select * from #localTemp;
/*
Output:
RNo Sc  Mat Eng
2	78	43	87
3	45	32	78
4	36	78	32
5	12	22	67
6	21	65	43
7	34	78	54
8	89	78	54
9	76	78	54
10	22	56	54
*/

-- Check original table
select * from Student_Marks;
/*
Output:
RNo Sc  Mat Eng
1	34	78	54
2	78	43	87
3	45	32	78
4	36	78	32
5	12	22	67
6	21	65	43
7	34	78	54
8	89	78	54
9	76	78	54
10	22	56	54
*/

-- Observation :  There is no impact on original table, 
           -- yaha RollNo 1 exist kar raha hai
		     -- jab we deleted RollNo=1 from temprary table.
-- There will be no impact on original table.
```
### Aapka table drop kab honga.
1. jab aap connection/session close kar de.
2. drop table #localTemp i.e Temprary_tableName;
### Create temprary table directly
```sql
use MyDatabase;

--Create  temprary table directly
Create table #TempStudent
(
	RollNo Int,
	City Varchar(100)
)

-- Insert data
Insert into #TempStudent(RollNo,City) Values(1,'London');

--Check data
Select * from #TempStudent;
/*
Output:
RNo  City
1	London
*/

```
![Alt text](image-83.png)
### Drop this table via direct command
Drop Table #TempStudent;
- table drop
### How to create global Temprary table.
```sql
use MyDatabase;

--Create  Global Temprary Table
Create table ##GlobalTempStudent
(
	RollNo Int,
	City Varchar(100)
)
```
![Alt text](image-84.png)
```sql
-- Insert data
Insert into ##GlobalTempStudent(RollNo,City) Values(1,'Delhi');
Insert into ##GlobalTempStudent(RollNo,City) Values(2,'London');
Insert into ##GlobalTempStudent(RollNo,City) Values(3,'London');

--Check data
Select * from ##GlobalTempStudent;
/*
Output:
RNo  City
1	Delhi
2	London
3	London
*/
```
### Hamara global temp table kisi bhi session/connection mein access ho jata hai.
![Alt text](image-85.png)
### Drop kab honga
- sabhi connection close ho jaye.Jo isse use kar rahe hai to automatic GlobalTempTable drop ho javenga.
- Manually drop bhi kar sakte like local temp table.
# 8. Sql Select Statement with Comparison operator
![Alt text](image-86.png)
![Alt text](image-87.png)
- db se data ko fetch karne ke liye select statement use karte
```sql
/*
Select Statement
   - Specific row
   - all row
   - Top n row
   - Top n% of row
   - Distinct row
*/
Use MyDatabase;

Create Table Employee
(
	empId Int,
	empName Varchar(50),
	dept Varchar(20),
	salary Int,
	City Varchar(50),
	joinYear Int
)

Insert into Employee(empId,empName,dept,salary,City,joinYear)
					Values(1005,'Linda','IT',3200,NULL,2022);
Insert into Employee(empId,empName,dept,salary,City,joinYear) 
					Values(1006,'Tony','HR',6700,'Delhi',1990);
Insert into Employee(empId,empName,dept,salary,City,joinYear) 
					Values(1007,'Joshep','Account',7800,'Delhi',2020);
Insert into Employee(empId,empName,dept,salary,City,joinYear) 
					Values(1009,'Alice','Sales',2100,'London',2021);
Insert into Employee(empId,empName,dept,salary,City,joinYear)  
				Values(1009,'Mangu','IT',2200,NULL,2022);
Insert into Employee(empId,empName,dept,salary,City,joinYear)  
			Values(1010,'David','HR',1100,'Dhaka',2022);
Insert into Employee(empId,empName,dept,salary,City,joinYear)  
				Values(1011,'Taylor','Dev',78966,'NewYork',2022);
Insert into Employee(empId,empName,dept,salary,City,joinYear) 
					Values(1012,'Mike','Dev',7654,'DC',2019);
Insert into Employee(empId,empName,dept,salary,City,joinYear) 
						Values(1013,'Susan','Welfare',7538,'London',2022);
Insert into Employee(empId,empName,dept,salary,City,joinYear) 
					Values(1014,'Zacab','IT',6886,'Kabul',2018);
Insert into Employee(empId,empName,dept,salary,City,joinYear) 
					Values(1015,'Minton','IT',6789,'Kabul',2012);

--To fetch all rows
Select * from Employee;
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mike	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
1015	Minton	IT		6789	Kabul	2012
*/

-- Fetch specific row
   -- humko keval empId aur empName hi chaiye
Select empId,empName from Employee;
/*
1005	Linda
1006	Tony
1007	Joshep
1009	Alice
1009	Mangu
1010	David
1011	Taylor
1012	Mike
1013	Susan
1014	Zacab
1015	Minton
*/

-- Humko yadi iska order change karna hai
  -- empName ko pehle display karna hia
Select empName,empId,dept,salary,joinYear from Employee;
/*
Linda	1005	IT	3200	2022
Tony	1006	HR	6700	1990
Joshep	1007	Account	7800	2020
Alice	1009	Sales	2100	2021
Mangu	1009	IT	2200	2022
David	1010	HR	1100	2022
Taylor	1011	Dev	78966	2022
Mike	1012	Dev	7654	2019
Susan	1013	Welfare	7538	2022
Zacab	1014	IT	6886	2018
Minton	1015	IT	6789	2012
*/

--Observation : 
     -- Ye kahli display ki liye hota hai
	 -- but physical table par iska koyi impact nahi hota.
	 -- yaha resultSet data ko change karke aapko data show karta hai.

--Data bahut jyada hota hai
  -- hume sirf specific number of data hi dekhna hai
    -- only 4 records hi dekhna hai tab
Select Top 4 * from Employee;
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021

observation:
    Employee Table ek resultSet create karenga.
	 ye resultSet 4 row ko show kar denga.
*/

-- aap * ki jagah column ka name bhi de sakte
Select Top 2 empId,empName from Employee;
/*
1005	Linda
1006	Tony
*/

-- Jo bhi Entire hamara ResultSet hai 
   -- uska hume 20% ye 50% hi data dekhna hai
Select Top 2 Percent * from Employee;
--Ouptut:
--1005	Linda	IT	3200	NULL	2022

-- 20% of specific data
Select Top 20 Percent empName from Employee;
/*
Linda
Tony
Joshep
*/
```
### About distinct
```sql
--Total Dept kitne hai? kyuki dept mein kafi repeat ho rahe hai.
  -- mane unique value nikalni hai
    -- so use Distinct
-- Select Distinct Which_Col_Unique_Value_U_Requrie from Table
Select Distinct dept from Employee;
/*
Account
Dev
HR
IT
Sales
Welfare

Observation:
   Repeated chije na dikhake, unique value ko display kar diya.
*/

-- hume multiple col ki uniuque value ko display karana hai
 -- dept aur empId  isko mila  kar ke 
     -- unique value ko generate karenga.
 Select Distinct dept,empId from Employee;
 /*
Account	1007
Dev		1011
Dev		1012
HR		1006
HR		1010
IT		1005
IT		1009
IT		1014
IT		1015
Sales	1009
Welfare	1013

-- Observation:
     -- Total hamare paas 11 record hai
	 -- empId unique hai and combo mein sare unique hi hia.
 */

  Select Distinct dept,city from Employee;
  /*
Account	Delhi
Dev		DC
Dev		NewYork
HR		Delhi
HR		Dhaka
IT		NULL
IT		Kabul
Sales	London
Welfare	London

Observation:
       - abhi 9 records hi mil rahe hai.
	   - city aur dept mein unique value 9 hai aur 2 repeated value hai..
	          isiliye usko diplay nhi kiya gya
			  IT NULL
			  IT Kabul  - ye duplicacy hai
  */
```
### Concept of fully qualified name
```sql
-- Concept of full qualified name
   -- Employee table hamare MyDatabase mein create hai
   -- yadi aapne current database change kar liya

   -- 1) via command
   create database TestDatabase;
   use TestDatabase;
```
### 2) via ui
![Alt text](image-88.png)
```sql
 -- and try
   Select * from Employee;
   --Error: Invalid object name 'Employee'.

   --DatabaseName.UserName.TableName  = Fully qualified Name
    Select * from MyDatabase.dbo.Employee;
	/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mike	Dev		7654	DC	2019
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
1015	Minton	IT		6789	Kabul	2012
	*/
```
### Where clause
- data ko filter karne ke liye, 
- data ko limit karne ke liye 
- resultset ko narrow karne ke liye, we use where clause
![Alt text](image-89.png)
```sql
Use MyDatabase;
/*
Where clause
   Comparison operator: =,>,>=,<,<=,<>
*/
Select  * from Employee;

-- hume sirf slective data ko check karna hai
  -- Hume pura record nikalna hai jiska empId 1005 hai
Select * from Employee Where empId = 1005;
--1005	Linda	IT	3200	NULL	2022

-- find record whose name is Linda
Select * from Employee Where empName='Linda';
--1005	Linda	IT	3200	NULL	2022

-- find record whose dept is IT
Select * from Employee Where dept='IT';
/*
1005	Linda	IT	3200	NULL	2022
1009	Mangu	IT	2200	NULL	2022
1014	Zacab	IT	6886	Kabul	2018
1015	Minton	IT	6789	Kabul	2012
*/

--Greater Than operator
--Jiski 4K ke upar salary hai unke naam
Select * from Employee Where salary > 4000;
/*
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1011	Taylor	Dev		78966	NewYork	2022
1012	Mike	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
1015	Minton	IT		6789	Kabul	2012
*/

--Greater than equal to
-- jiska salary 7800 utni ya usse upar ho
Select * from Employee Where salary >= 7800;
/*
1007	Joshep	Account	7800	Delhi	2020
1011	Taylor	Dev		78966	NewYork	2022
*/

--Less than
--  salary less than 4K
Select * from Employee Where salary < 4000;
/*
1005	Linda	IT		3200	NULL	2022
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
*/

--less than equal to
--    find sale less than equal to 3200
Select * from Employee Where salary <= 3200;
/*
1005	Linda	IT		3200	NULL	2022
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
*/

--Not equal
-- 3200 nahi hai jinki sal
Select * from Employee Where salary <> 3200;
/*
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mike	Dev		7654	DC	    2019
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
1015	Minton	IT		6789	Kabul	2012
*/
```

### Logical operator with where clause
- multiple condition ko join karne ke liye, where clause ke sath AND use karte hai.
- Between operator, particualr value search karta hai from the set of values.

![Alt text](image-90.png)
```sql
/*
Logical operators
    AND	, OR, IN, BETWEEN,EXISTS,LIKE,NOT,IS NULL
*/
Select * from Employee;
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mike	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
1015	Minton	IT		6789	Kabul	2012
*/

-- AND operator
-- Hume wo employee chaiye jinki city Delhi aur sal 3k se upar
Select * from Employee where City='Delhi' AND salary > 3000;
/*
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020

Observation:
   Yadi aapki dono condition satisfy ho gyi.
     tabhi wo data resultSet mein add kar denga
	  and aap result set ko dekh paonge.
*/

--OR operator
-- Hume wo employee chaiye jinki city Delhi ho ya sal 3k se upar ho
Select * from Employee where City='Delhi' OR salary > 3000;
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1011	Taylor	Dev		78966	NewYork	2022
1012	Mike	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
1015	Minton	IT		6789	Kabul	2012
*/

--Between Operator
-- 2K aur 5K  ke bich ke salary nikalni hai 
Select * from Employee where  salary  BETWEEN 2000 AND 5000;
/*
1005	Linda	IT		3200	NULL	2022
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022

 ye dono value include hoti hai search mein
   indono ke range ki bich ki value add hongi result set mein
*/

Select * from Employee where  salary  BETWEEN 1100 AND 3200;
/*
1005	Linda	IT		3200	NULL	2022
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022

1100(minimum range) bhi include hue
  3200(maximum range) bhi
   aur unke bich ki sal bhi result set mein add hue
*/

--Exist operator
  -- return type true or false
   -- use with condtions
IF EXISTS(Select * from Employee where empId=1001)
Print 'YES'
ELSE
Print 'NO'
--Output : NO

IF EXISTS(Select * from Employee where empId=1007)
Print 'YES'
ELSE
Print 'NO'
--Output : YES

--NOT operator
  -- apke logical operator ke menaing ko reverse kar deta hai
IF NOT EXISTS(Select * from Employee where empId=1007)
Print 'YES'
ELSE
Print 'NO'
--Output : NO

--IS NULL
 -- Null value or blank ke andar diff hota hai

 -- For blank
 Select * from Employee where city='';
 -- Output: Since we dont have any record whose city is blank, so no data 
      -- but query is fine 

-- for null
 Select * from Employee where city is null;
 /*
 1005	Linda	IT	3200	NULL	2022
1009	Mangu	IT	2200	NULL	2022
 */

 -- Like operator
   -- used for complex searching
-- wo empName jiska starting charcter A hai
Select * from Employee where empName LIKE 'A%';
/*
LIKE 'A%';
      % ye ek sustitue hai dusri value ke liye
Jise A se name start hua, uska baad ka character kuch bhi ho sakta hia
    % usse replace marta.

1009	Alice	Sales	2100	London	2021
*/

-- aisa name fetch karo, jisme D letter exist karta ho 
    -- kisi bhi position par
Select * from Employee where empName LIKE '%D%';
/*
1005	Linda	IT	3200	NULL	2022
1010	David	HR	1100	Dhaka	2022
*/

-- aisa name fetch karo, jisme D letter exist karta ho 
    -- last position par
Select * from Employee where empName LIKE '%D';
/*
1010	David	HR	1100	Dhaka	2022
*/
```
# 9. Like Command
- like operator ye ek logical operator hai
- jo string ko kisi pattern ke sath match karne ka kam karta hai
- pattern may be expression or wild card char
- eg emp name search karna hai joh A se suru hote hai.

![Alt text](image-91.png)
- like operator ke sath kisi bhi character String ko pattern ke sath match karte.

![Alt text](image-92.png)
```sql
use MyDatabase;
/*
	Wild Character :  % (Percent)
	    % means any String of 0 or more character
*/
Select * from Employee;
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mike	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
1015	Minton	IT		6789	Kabul	2012
*/
-- Find Employee details whose name is Linda
Select * from Employee where empName = 'Linda';
--1005	Linda	IT	3200	NULL	2022

--Find employee details whose name starts with a character like a
  -- aise query ke liye use karte hai like operator with pattern
Select * from Employee where empName Like 'a%';
/*
1009	Alice	Sales	2100	London	2021

   a% - a ke kitne bhi charcter ho, but pehla a ho
*/

--Find employee details whose name starts with a character like ma
Select * from Employee where empName Like 'ma%';
--1009	Mangu	IT	2200	NULL	2022

--Find employee details whose name ends with a character like a
Select * from Employee where empName Like '%a';
--1005	Linda	IT	3200	NULL	2022

--Find employee details whose name ends with a character like ab
Select * from Employee where empName Like '%ab';
--1014	Zacab	IT	6886	Kabul	2018

--Find employee details whose name contains a
   -- kisi bhi position par ho a
Select * from Employee where empName Like '%a%';
/*
1005	Linda	IT		3200	NULL	2022
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
*/
```
### Underscore
```sql
/*
	Wild card : _ Underscore
	_  ==> It represent single charcter
*/
-- aisa empName jisme 1 hi charcter ho
Select * from Employee where empName like '_';
-- Output: Query executed succssfully but in our db no employee having 
   -- single charcter name

-- aisa empName jisme 4 hi charcter ho
Select * from Employee where empName like '____';
/*
1006	Tony	HR	6700	Delhi	1990
1012	Mike	Dev	7654	DC		2019

so 4 baar underscore use kiya hai query mein.
*/

-- aisa empName jisme 4 hi charcter ho aur uska starting charcter T se suru ho
Select * from Employee where empName like 'T___';
/*
1006	Tony	HR	6700	Delhi	1990

T___ ===> T ke sath 3 underscore liye.
*/
```
### More wildcard charcters
```sql
/*
	Wildcard - [list of charcter]
	  Represents any single charcter within specified set
*/

-- Hume multiple name lene hai
   -- jiska name a l m se start hota hai
Select * from Employee where empName like '[alm]%';
/*
1005	Linda	IT		3200	NULL	2022
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1012	Mike	Dev		7654	DC		2019
1015	Minton	IT		6789	Kabul	2012

[alm]% ==> a se, l se and m se start hota ho wo sare name
*/

/*
	WildCard : ^ Negate Operator
*/

-- hume aise name chaiye 
   -- jiska charcter a/l/m se suru nhi hota hai
    -- isko chodke sare name

Select * from Employee where empName like '[^alm]%';
/*
1006	Tony	HR		6700	Delhi	1990
1007	Joshep	Account	7800	Delhi	2020
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1013	Susan	Welfare	7538	London	2022
1014	Zacab	IT		6886	Kabul	2018
*/

/*
	Wildcard [charcter-charcter]:
	   represents any single charcter within the specfied range.
*/
--hume wo sare name chiaye
  -- jo ki a se lekar d tak aate ho
Select * from Employee where empName like '[a-d]%';
/*
1009	Alice	Sales	2100	London	2021
1010	David	HR		1100	Dhaka	2022

[a-d] ==> a-d tak ke range ke 
   mane isme a,b,c,d 
     agar koyi name start ho raha hai a/b/c/d 
to wo result set me aa javenga.
*/

--hume wo sare name chiaye
  -- jo ki a se lekar m tak aate ho
Select * from Employee where empName like '[a-m]%';
/*
1005	Linda	IT		3200	NULL	2022
1007	Joshep	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1012	Mike	Dev		7654	DC		2019
1015	Minton	IT		6789	Kabul	2012
*/
```
# 10. Exist and Not Exist sub queries in sql
- kisi value ko table mein check karna
- ki vo value table mein exist karti hai ya nahi

![Alt text](image-93.png)
![Alt text](image-94.png)
```sql
use MyDatabase;

update  Employee set empName='Joshef' where empId=1007;
update  Employee set empName='Mikea' where empId=1012;
update  Employee set empName='Mac_Son' where empId=1014;
update  Employee set empName='Mac_Gill' where empId=1015;

select * from Employee;
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshef	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mikea	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Mac_Son	 IT		6886	Kabul	2018
1015	Mac_Gill IT		6789	Kabul	2012
*/

Select 1;
/*
   1  - Result me aa raha hai
   aur message mein (1 row affected)

   yaha return 1 row ho rahi hai
*/

Select 0;
/*
   0  - Result me aa raha hai
   aur message mein (1 row affected)

   yaha return 1 row ho rahi hai
*/

Select Null;
/*
   Null  - Result me aa raha hai
   aur message mein (1 row affected)

   yaha return 1 row ho rahi hai
*/
select * from Employee where EXISTS(Select 1);
select * from Employee where EXISTS(Select 0);
select * from Employee where EXISTS(Select Null);
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshef	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mikea	Dev		7654	DC	2	019
1013	Susan	Welfare	7538	London	2022
1014	Mac_Son	IT		6886	Kabul	2018
1015	Mac_Gill	IT	6789	Kabul	2012

1 row return ho rahi 
   mane exist ye true return kar raha hai.
*/

Create Table #temp
(
	Id Int
)

insert into #temp values(1);

Select * from #temp;
--1  id mein 1 aaya ResultSet ke andar

select * from Employee where EXISTS(Select Id from #temp);
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshef	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mikea	Dev		7654	DC	2019
1013	Susan	Welfare	7538	London	2022
1014	Mac_Son	IT		6886	Kabul	2018
1015	Mac_Gill	IT	6789	Kabul	2012
*/

-- ab yadi mein temprary table drop kardu 
drop table #temp;

--ab fhir se temp table create karte 
  -- par koyi row add nahi karte
Create Table #temp
(
	Id Int
)

Select Id from #temp
-- Result set mein kuch nhi aaya

-- ab select query chalao exist wali
select * from Employee where EXISTS(Select Id from #temp);
-- Query executed but no output is there

select * from Employee where EXISTS(Select empId from Employee where salary > 4000);
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshef	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mikea	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Mac_Son	IT		6886	Kabul	2018
1015	Mac_Gill	IT	6789	Kabul	2012

ye to sara data return kar raha hai
   since exist mein joh subquery chal rahi hai
     wo non zero row provide kar rahi hai

Select * from employee where Exist(subquery)

Select * from employee where True
   so return all thing

  Funda:
     0 row - false
	 1 or multiple - true
*/

-- for 0 row
select * from Employee where EXISTS(Select empId from Employee where salary > 80000);
/*
Query executed but blank output
 since subquery return 0 row
  for 0 row exist return false

 Select * from employee where Exist(subquery)

Select * from employee where False
   so return nothing
*/
```
```sql
use MyDatabase;
/*
   Exist in If condition
	How to use Exist operator with If condition
*/
If EXISTS(Select * from Employee where empId=1001)
 Begin
  Select * from  Employee where empId=1009
 End
Else 
 Begin
  Select * from  Employee where empId=1012
 End

/*
1012	Mikea	Dev	7654	DC	2019

Simple If-else condition
  yaha else block chala hai
*/

If EXISTS(Select * from Employee where empId=1005)
 Begin
  Select * from  Employee where empId=1009
 End
Else 
 Begin
  Select * from  Employee where empId=1012
 End
/*
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022

Yaha If block chal gya 
  since condition is true.
*/

/*
	Not Exists
*/
If NOT EXISTS(Select * from Employee where empId=1005)
 Begin
  Select * from  Employee where empId=1009
 End
Else 
 Begin
  Select * from  Employee where empId=1012
 End
/*
1012	Mikea	Dev	7654	DC	2019

Not exists reverse kar denga output ko
  isiliye yaha else chalenga.
*/
```
### Co-related query
- depened on outer query
- ye main query ke data ko use karti hai, uske refrence ko use karti hai
- isiliye isko corelated subquery kehte hai

### Diff
### 1. Non correlated query 
- aap isse indiviudal/independently  execute kar sakte hai.

### 2. Corelated subquery
- aap isse indiviudal/independently  execute nhi kar sakte hai.
- kyuki iske andar refrence outer query ka use hota hai.

![Alt text](image-95.png)
- aapke main table aapke 10 record hai
- to har baar 1 row ke liye 10 baar sub query execute hongi.
- mane 10*10 = 100 baar subquery chalengi.

![Alt text](image-96.png)
```sql
/*
	EXISTS Corelated subquery
*/

--Non corelated subquery
Select * from Employee where EXISTS(Select * from Employee where salary > 7000);
/*
1005	Linda	IT		3200	NULL	2022
1006	Tony	HR		6700	Delhi	1990
1007	Joshef	Account	7800	Delhi	2020
1009	Alice	Sales	2100	London	2021
1009	Mangu	IT		2200	NULL	2022
1010	David	HR		1100	Dhaka	2022
1011	Taylor	Dev		78966	NewYork	2022
1012	Mikea	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022
1014	Mac_Son	IT		6886	Kabul	2018
1015	Mac_Gill	IT	6789	Kabul	2012

Jo subquery hai wo non zero element return kar rahi hai.
 so Exists mein true aaya
Thats why sare records display ho rahe hai ResultSet mein

ye jo subquery individually bhi run ho rahi hai

yaha sara data show ho raha hai
*/

-- Ab meri requirement hai
  -- ki Exist ke sath mein wohi data aaye
    -- jo subquery mein aa raha hai.
     -- for that use co-related subquery

 -- coreleated subquery mein jo data hota hai
     -- wo outer query ke data ko reflect karta hai
Select * from Employee emp 
	where EXISTS(Select * from Employee 
	    where 
		   empId=emp.empId AND salary > 7000);
/*
1007	Joshef	Account	7800	Delhi	2020
1011	Taylor	Dev		78966	NewYork	2022
1012	Mikea	Dev		7654	DC		2019
1013	Susan	Welfare	7538	London	2022

empId --> ye subquery se hai 
  emp --> alias name
emp.empId --> ye outerquery se hai (ye outer query ke col ko refer karenga)

Hume data wohi mil raha jiski salary 7k se upar hai.

ye query outer query ke ref ke bina execute ho nhi sakti

And operation ke wajah se hume desired data mil raha hai.
*/
```
### Corelated subquery kaam kaise kar rahi hai.
![Alt text](image-97.png)
- CQT se empId 1001 MQT se compare karenga
- yadi match kar gya tab salary comparison honga
- to 3k > 5k false, so data add nhi honga resultset mein
- fhir CQT ka empId 1001 MQT ke remaining empId se compare honga
- match na hone ke karan, koyi data rst mein add nhi honga.

![Alt text](image-98.png)
- CQT se empId 1002 MQT se compare karenga
- yadi match kar gya tab salary comparison honga
- to 4k > 5k false, so data add nhi honga resultset mein
- fhir CQT ka empId 1002 MQT ke remaining empId se compare honga
- match na hone ke karan, koyi data rst mein add nhi honga.

![Alt text](image-100.png)
- CQT se empId 1003 MQT se compare karenga
- yadi match kar gya tab salary comparison honga
- to 6k > 5k true, so data add  honga resultset mein
- fhir CQT ka empId 1003 MQT ke remaining empId se compare honga
- match na hone ke karan, koyi data rst mein add nhi honga.

![Alt text](image-99.png)
![Alt text](image-101.png)
![Alt text](image-102.png)
![Alt text](image-103.png)
# 11. Foreign key with Cascade Delete and update.
- 2 table ke andar yadi aapka primary key aur foreign key ka relationship hai.
- So aap yadi master table se koyi data ko delete karte ho
- to uska related data jo child table mein hai wo automatically delete hota hai.
-In case of cascade.

![Alt text](image-104.png)
- On Delete Cascade/ On update cascade both are optional
- iske sath action hote hai, jaise in case of delte cascade
-  no action/  cacade / set null /set defualt

- by default no action hota hai
-  In case of No Action ==> master table se wo row ka data aap delete nhi kar sakte jiska refrence child table mein hai. Normal behaviour.
- Cascade ==> parent table se data delete to child se bhi honga
- Set NUll ==> Parent table mein foreign key ke value wo Null set kar denga. So data delete nhi hua, but fk null ho gyi..
- Set Default ==> Parent table se data delete honga but child table mein col ke defualt value set ho javengi.

![Alt text](image-105.png)
![Alt text](image-106.png)
```sql
use MyDatabase;

--Parent_ child relation create karte.

Create table Customers
(
	Cust_Id Int Primary Key,
	Cust_Name Varchar(100)
)

Insert into Customers(Cust_Id,Cust_Name) Values(1,'Singh');
Insert into Customers(Cust_Id,Cust_Name) Values(2,'John');
Insert into Customers(Cust_Id,Cust_Name) Values(3,'Smith');
Insert into Customers(Cust_Id,Cust_Name) Values(4,'Linda');

Create table Orders
(
	Order_Id Int Identity(1,1),
	cust_Id Int,
	Item Varchar(100)
	FOREIGN KEY(cust_Id) REFERENCES Customers(Cust_Id) 
)

-- once relationship established
 -- hum wohi data Order table mei daal sakte
   -- mane jo cust_id Customers table mein hongi
    -- ussi se related id aur item hum Order mein daal pavenge.
Insert Into Orders(cust_Id,Item) values (1,'Pen');
Insert Into Orders(cust_Id,Item) values (2,'Mouse');
Insert Into Orders(cust_Id,Item) values (2,'Keyboard');
Insert Into Orders(cust_Id,Item) values (3,'CPu');
Insert Into Orders(cust_Id,Item) values (4,'Pad');

--ek aisi value ki cust_id insert karte jo 
 -- Customers table mein exist nahi karti ho.
Insert Into Orders(cust_Id,Item) values (10,'Pad');
/*
Error:
The INSERT statement conflicted with the FOREIGN KEY constraint
"FK__Orders__Item__2A164134". The conflict occurred in database "MyDatabase",
table "dbo.Customers", column 'Cust_Id'.
*/

--Check data
Select * from Customers;
/*
1	Singh
2	John
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
1		1	Pen
2		2	Mouse
3		2	Keyboard
4		3	CPu
5		4	Pad
*/

--Default behaviour ==> NO action
-- Yadi hum parent table se koyi data delete karte hai
  -- tab child table se data delte hota hai?
delete from Customers where Cust_Id=1;
/*
The DELETE statement conflicted with the REFERENCE constraint "FK__Orders__Item__2A164134".
The conflict occurred in database "MyDatabase", table "dbo.Orders", column 'cust_Id'.

Nhi delete karne diya.
  jis key ko hum delete kar rahe hai
    wo key hamara child table mein exist karta hai so conflict paida honga.
*/
```
### ON Delete CAscade
```sql
-- requirement 
-- hum parent table se key delete karte hai yadi
 -- to uska child table ka key bhi delete ho jave
   -- use Option of On Cascase Delete 
    -- we have 2 option for this
	 -- 1. Table Alter kare
	 -- 2. Table Drop karke iski defination ko change kare.

--2) let's drop child table 
   -- and recreate it while changing it's defination
drop table Orders;

Create table Orders
(
	Order_Id Int Identity(1,1),
	cust_Id Int,
	Item Varchar(100)
	FOREIGN KEY(cust_Id) REFERENCES Customers(Cust_Id) 
	ON DELETE CASCADE
)
/*
aB iska behaviour aisa honga.
   ki apne parent table se key delete kari
    to child table se bhi apne aap wo key delete ho javengi
*/

--Now insert the data
Insert Into Orders(cust_Id,Item) values (1,'Pen');
Insert Into Orders(cust_Id,Item) values (2,'Mouse');
Insert Into Orders(cust_Id,Item) values (2,'Keyboard');
Insert Into Orders(cust_Id,Item) values (3,'CPu');
Insert Into Orders(cust_Id,Item) values (4,'Pad');

--Check data
Select * from Customers;
/*
1	Singh
2	John
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
1		1	Pen
2		2	Mouse
3		2	Keyboard
4		3	CPu
5		4	Pad
*/

-- Now delete sth from master table and check the result
  -- parent se id 1 delte
delete from Customers where Cust_Id=1;
-- 1 row affected

--Check data
Select * from Customers;
/*
2	John
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
2		2	Mouse
3		2	Keyboard
4		3	CPu
5		4	Pad
*/
/*
 On Delete Cascade mein data child table se bhi delete ho jata hai
*/
```
### Set NULL
```sql
-- meri requirement 
 -- Parent table se data delete ho jave
  -- but child table se key ye Null set ho jave.

drop table Orders;

Create table Orders
(
	Order_Id Int Identity(1,1),
	cust_Id Int,
	Item Varchar(100)
	FOREIGN KEY(cust_Id) REFERENCES Customers(Cust_Id) 
	ON DELETE SET NULL
)

-- Insert data
 -- Remember: cust_Id 1 ye master table se delete ho chuka hai.So ignore it
Insert Into Orders(cust_Id,Item) values (2,'Mouse');
Insert Into Orders(cust_Id,Item) values (2,'Keyboard');
Insert Into Orders(cust_Id,Item) values (3,'CPu');
Insert Into Orders(cust_Id,Item) values (4,'Pad');

--Check data
Select * from Customers;
/*
2	John
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
1		2	Mouse
2		2	Keyboard
3		3	CPu
4		4	Pad
*/

--delete sth from master table and see result
delete from Customers where Cust_Id=2;

--Check data
Select * from Customers;
/*
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
1	  NULL	Mouse
2	  NULL	Keyboard
3		3	CPu
4		4	Pad

Yaha child table i.e Order table mein
 customer_id ka column mein 
   particular value null set ho gyi
*/
```
### Set Default
```sql
drop table Orders;
drop table Customers;

Create table Customers
(
	Cust_Id Int Primary Key,
	Cust_Name Varchar(100)
)

Insert into Customers(Cust_Id,Cust_Name) Values(1,'Singh');
Insert into Customers(Cust_Id,Cust_Name) Values(2,'John');
Insert into Customers(Cust_Id,Cust_Name) Values(3,'Smith');
Insert into Customers(Cust_Id,Cust_Name) Values(4,'Linda');

-- aap chahte hai
  -- ki parent table se data to delete ho jave
  -- lekin child table mein Instead of Null value 
  -- default value set ho jave.

Create table Orders
(
	Order_Id Int Identity(1,1),
	cust_Id Int NOT	NULL DEFAULT 1,
	Item Varchar(100)
	FOREIGN KEY(cust_Id) REFERENCES Customers(Cust_Id) 
	ON DELETE SET DEFAULT
)
/*
  	cust_Id Int NOT	NULL DEFAULT 1,==> 
	    1 ye wo key hai jo aapka master table mein hai..
	yaha par aap koyi bhi wo key mention kar sakte jo Master table mein hai
	 since child table mein jo FK hai 
	   basically wo master table ki primary key hai 
*/
Insert Into Orders(cust_Id,Item) values (1,'Pen');
Insert Into Orders(cust_Id,Item) values (2,'Mouse');
Insert Into Orders(cust_Id,Item) values (2,'Keyboard');
Insert Into Orders(cust_Id,Item) values (3,'CPu');
Insert Into Orders(cust_Id,Item) values (4,'Pad');


--Check data
Select * from Customers;
/*
ciD  cName
1	Singh
2	John
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
1		1	Pen
2		2	Mouse
3		2	Keyboard
4		3	CPu
5		4	Pad
*/

-- ab yadi hum master table se custid 2 delete kare
  -- so child table mein custId 2 ke jagah
   -- default id 1 aane ko hona
delete from Customers where Cust_Id=2;

--Check data
Select * from Customers;
/*
ciD  cName
1	Singh
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
1		1	Pen
2		1	Mouse
3		1	Keyboard
4		3	CPu
5		4	Pad
*/
```
### On Update
```sql
--ON Update
drop table Orders;
drop table Customers;

Create table Customers
(
	Cust_Id Int Primary Key,
	Cust_Name Varchar(100)
)

Insert into Customers(Cust_Id,Cust_Name) Values(1,'Singh');
Insert into Customers(Cust_Id,Cust_Name) Values(2,'John');
Insert into Customers(Cust_Id,Cust_Name) Values(3,'Smith');
Insert into Customers(Cust_Id,Cust_Name) Values(4,'Linda');

--child table mein change kare
Create table Orders
(
	Order_Id Int Identity(1,1),
	cust_Id Int,
	Item Varchar(100)
	FOREIGN KEY(cust_Id) REFERENCES Customers(Cust_Id) 
	ON UPDATE CASCADE
)
/*
	ON UPDATE CASCADE ==>
	  Yadi aapka master table mein primary key mein change hota hai
	    to uska reflection child table mein bhi aavenga.
*/

Insert Into Orders(cust_Id,Item) values (1,'Pen');
Insert Into Orders(cust_Id,Item) values (2,'Mouse');
Insert Into Orders(cust_Id,Item) values (2,'Keyboard');
Insert Into Orders(cust_Id,Item) values (3,'CPu');
Insert Into Orders(cust_Id,Item) values (4,'Pad');


--Check data
Select * from Customers;
/*
ciD  cName
1	Singh
2	John
3	Smith
4	Linda
*/

Select * from Orders;
/*
Or_id  C_id Item
1		1	Pen
2		2	Mouse
3		2	Keyboard
4		3	CPu
5		4	Pad
*/

-- Yadi hum master table mein custId 2 ki jagha 25 karte hai
  -- to child table mein bhi 25 custId reflect hona mangta
   -- instead of 2
Update Customers set Cust_Id = 25 where Cust_Id=2;

--Check data
Select * from Customers;
/*
ciD  cName
1	Singh
3	Smith
4	Linda
25	John
*/

Select * from Orders;
/*
Or_id  C_id Item
1		1	Pen
2		25	Mouse
3		25	Keyboard
4		3	CPu
5		4	Pad
*/
```
# 12. Sql String function

