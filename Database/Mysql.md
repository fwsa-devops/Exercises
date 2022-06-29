# MySQL Exercises


### Database

Task 1 : Create a database Academy :
```
CREATE DATABASE Academy;
```

Task 2: List the databases created till now in the server :
```
SHOW DATABASES;
```

Task 3: Use the database Academy
```
USE Academy;
```

Task 4: Drop the database Academy:
```
DROP DATABASE Academy;
```


### Table 

Task 1: List the tables inside a database :
```
SHOW TABLES;
```

 Task 2: Create a table 'Students' with following validations ( also check the class>= 1 and class<=12) :
```
CREATE TABLE student(
           id tinyint PRIMARY KEY auto_increment,
           name varchar(20) NOT NULL,
           class tinyint CHECK(class>=1 and class<=12) NOT NULL
);
```

 Task 3: List the validations of all attributes inside the table `Students`:
```
DESC Students
Or
DESCRIBE Students
```


 Task 5: Insert rows into 'student' table :
```
INSERT INTO Students VALUES(1,"Chitra",10");
Or
INSERT INTO Students(name,class) VALUES("Chitra",10);
Or
INSERT INTO Students VALUES(1,"Chitra",10),(2,"Aswath",12);
```


Task 6: Update the class as "12" for the student with id "1" in student table :
```
UPDATE Students SET class = 12 WHERE id = 1;
```


 Task 7: Add a new column "section varchar(20) not null" to the "student" table after the "class" column:
```
ALTER TABLE Students ADD column section varchar(20) NOT NULL AFTER class;
```


Task 8: Change the datatype size for the "name" column of "student" table to varchar(30) :
```
ALTER TABLE Students MODIFY name varchar(30) NOT NULL;
Or
ALTER TABLE Students CHANGE name varchar(30) NOT NULL;
```


Task 9: Change the table name "student" to "Students" :
```
ALTER TABLE student RENAME TO Students;
```

Task 10: Change the column name "class" to "Class" of table "student" :
```
ALTER TABLE Students CHANGE class Class tinyint NOT NULL;
Or
ALTER TABLE Students RENAME COLUMN class to Class; --> Best
```

Task 11: Create a child table 'mark_list' of 'student' table with following validations :
```
CREATE TABLE mark_list(id tinyint,roll_no tinyint UNIQUE,marks tinyint default 0,FOREIGN KEY(id) REFERENCES Students(id));
Or
CREATE TABLE mark_list(id tinyint,roll_no tinyint UNIQUE,marks tinyint default 0,FOREIGN KEY(id) REFERENCES Students(id) ON DELETE CASCADE ON UPDATE CASCADE);
```

Task 12: Drop the primary key constraint from the "student" table :
```
ALTER TABLE Students DROP PRIMARY KEY;
```

Task 13: Drop "section" column from "student" table :
```
ALTER TABLE Students DROP COLUMN section;
```

Task 14: Delete the rows from the "student" table whose names start with L and ends with R :
```
DELETE FROM Students WHERE name LIKE("L%R");
```


Task 15: Delete all the rows from the "student" table permanently :
```
TRUNCATE TABLE Students;
```


Task 16: Drop the table 'mark_list' :
```
DROP TABLE mark_list;
```


### Operators

Task 1: List of all students whose id is in range [3,10] from 'student' table:

```
SELECT name FROM Students WHERE id BETWEEN 3 AND 10;
Or
SELECT name FROM Students WHERE id >= 3 AND id <=10;
```




Task 2: List the names of students whose name starts with P or name having only 3 letters in it :
```
SELECT name FROM Students WHERE name LIKE("L%") or name LIKE("___");
```

Task 3: List the details of students who has not updated their class details :
```
SELECT * FROM Students WHERE class is NULL;
Or
SELECT * FROM Students WHERE class = NULL;
```



  Task 4: List the students whose class is either 11 or 10 :
```
SELECT name FROM Students WHERE class = 11 OR class = 10;
Or
SELECT name FROM Students WHERE class IN(11,10);
```

Task 5: List the student details who does not belong to class 12 :
```
SELECT * FROM Students WHERE class !=12;
or
SELECT * FROM Students WHERE class NOT IN(12);
```

 Task 6: Perform some arithmetic calculations :
```
SELECT 4+3;
SELECT 4*3,4/3,4-3,4%3;
```

### Aggregate functions

 Task 1: List the total marks and te average marks scored by the whole school from "mark_list" table 
```
SELECT SUM(marks),AVG(marks) FROM mark_list;
```

 Task 2: List the minimum scorer and maximum scorer as minimum and maximum from "mark_list" table
```
SELECT MIN(marks) MINIMUM,MAX(marks) MAXIMUM FROM mark_list;
Or
SELECT MIN(marks) AS MINIMUM,MAX(marks) AS MAXIMUM FROM mark_list;
```


Task 3: List the number of students studying in the school 
```
SELECT COUNT(*) FROM Students;
```


Task 4: List the number of different number of classes from "student" table
```
SELECT COUNT(DISTINCT(class)) FROM Students;
```


### Order by

 Task 1: List the marks of the students of the School in order least to maximum 
```
SELECT marks FROM Students ORDER BY marks ASC;
Or
SELECT marks FROM Students ORDER BY marks;
```


 Task 2: List the marks of the students of the School in order maximum to least :
```
SELECT marks FROM Students ORDER BY marks DESC;
```

### Group By 

 Task 1: List of number of students class wise from the table 'Students'
```
SELECT COUNT(*),class FROM Students GROUP BY class;
```


 Task 2: List of number of students in each class with at least 11 students in it from "student" table
```
SELECT COUNT(*),class FROM student GROUP BY class HAVING count(*)>=11;
```


 Task 3: List the number of students in each class with at least 11 students in it and class > 3 
```
SELECT COUNT(*),class FROM student WHERE class>3 GROUP BY class HAVING COUNT(*)>=11;
Or
SELECT COUNT(*),class FROM student GROUP BY class HAVING COUNT(*)>=11 AND class>3;
```


### Join 


 Task 1:  List the students and the marks scored by them by using "student" and "mark_list" tables 
```
SELECT st.name,ml.marks FROM students st INNER JOIN mark_list ml ON st.id = ml.id;
Or
SELECT st.name,ml.marks FROM students st INNER JOIN mark_list ml USING id;
```


 Task 2:  List the students and the marks scored by them by using "student" and "mark_list" tables and marks > 90
```
SELECT st.name,ml.marks FROM students st INNER JOIN join mark_list ml ON st.id=ml.id where marks>90;
Or
SELECT st.name,ml.marks FROM students st INNER JOIN mark_list ml ON st.id=ml.id and marks > 90;
```



 Task 3: List the students and the marks scored by them by using "student" and "mark_list" tables and marks > 90 (List even the students who didn't attend the exam):
```
SELECT st.name,ml.marks FROM students st LEFT JOIN mark_list ml ON st.id=ml.id WHERE marks>90;
```


 Task 4:  List all the possible combinations that data from student table make with data from mark_list table
```
SELECT * FROM student CROSS JOIN mark_list; --> Best
Or
SELECT * FROM student INNER JOIN mark_list; --> INNER JOIN without ON condition = CROSS JOIN
```


### Indexing 

 Task 1: Create an index as "idx_name" for the "name" column in "students" table :
```
CREATE INDEX id_name ON students(name);
```


 Task 2: Create a table coaches( id,name ) with id as clustered index
```
CREATE TABLE coaches(id int primary key,name varchar(20));
```


 Task 3: Declare unique index as idx_c_name for the name column in coaches table
```
CREATE UNIQUE INDEX idx_c_name ON coaches(name);
```


 Task 4: create a table coach_login(id foreign key,email varchar(20) with pattern ending as "gmail.com" and unique index as idx_email)
```
CREATE table coach_login(id int,email varchar(20) check(email like("%@gmail.com"),foreign key(id) references coaches(id), unique index idx_email(email)); 
```

 Task 15: Drop the index idx_c_name on coaches table :
```
drop index idx_c_name;
```









