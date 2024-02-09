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
# 4. 


 






