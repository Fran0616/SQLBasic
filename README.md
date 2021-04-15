# SQLBasic

Structured Query Language (SQL)
=

SQL is industry stadard languge for defining, manipulating, and retriving the data in a database. It was develop at IBM by Donald Chamberlin and Raymond Boyce in the early 1970s. SQL is not a complete programming language but a data sub language. It can be divided into two categories DDL, DML. Data Definition Language (DDL) statments used for creating tables, relationships, and other structures. Data Manipulation Language(DML) statemment used for queries and data modification. Select, insert, Delete, and update. More on DML can be found [here]()

CREATE TABLE statement is used for defining the scheme of the database. It consist of three parts. Column name, data type, and constraints. 

ie: 
```
CREATE TABLE TableNameHere(
column1 datatype constrain,
column2 datatype constrain,
CONSTRAIN PRIMARY KEY (column1),
 CONSTRAINT FOREIGN KEY(column2)
      REFERENCES SomeTableNameGoesHere(ColumnFromTable)

```
List of possible constraints are:

- PRIMARY KEY - may not have null value

- UNIQUE - values in a column must be unique; cant used repeated value

- NULL/NOT NULL - empty/not empty

- FOREIGN KEY - used to create referential integrity 

- CHECK - specefies what data value are allowed in a particular column

- REFERENTIAL CONTRAINT - Action to take when parent row is modified/deleted. 




Table Example:
- DEPARTMENT (DepartmentName(PK), BudgetCode, OfficeNumber, Phone)

- Employee(EmployeeNumber(PK), FirstName, LastName, DepartmentName(FK), Phone, Email) 

- Project(ProjectID(PK), Name, DepartmentName(FK), MaxHours, StartDate, EndDate)

- Assigment(ProjectID(PK), EmployNumber(PK), HoursWorked)


```
CREATE TABLE Department
   (DepartmentName varchar(20) NOT NULL,
   BudgetCode smallint NOT NULL,
   OfficeNumber smallint NOT NULL,
   Phone char(18),
   
   CONSTRAINT PK_Deparment PRIMARY KEY(DepartmentName)
   );


```

```
CREATE TABLE Employee
   (EmployeeNumber char(10) NOT NULL,
   FirstName varchar(18) NOT NULL,
   LastName varchar(18) NOT NULL,
   DepartmentName varchar(20),
   Phone char(18),
   Email varchar(50),

   CONSTRAINT PK_Employee PRIMARY KEY (EmployeeNumber),
   CONSTRAINT FK_Dept FOREIGN KEY(DepartmentName)
      REFERENCES DEPARTMENT(DepartmentName)
);


```


```
CREATE TABLE Assignment
   (ProjectID char(8) NOT NULL,
   EmployeeNumber char(10) NOT NULL,
   HoursWorked char(48),

   CONSTRAINT PK_Assignment PRIMARY KEY (PROJECTID, EmployeeNumber),
   CONSTRAINT FK_Proj FOREIGN KEY(ProjectID)
      REFERENCES PROJECT(ProjectID),
   CONSTRAINT FK_Emp FOREIGN KEY(EmployeeNumber)
      REFERENCES EMPLOYEE(EmployeeNumber)
);




```

```
CREATE TABLE Project
   (ProjectID char(8) NOT NULL,
   Name varchar(18) NOT NULL,
   DepartmentName varchar(20),
   MaxHous char(48),
   StartDate date NOT NULL,
   EndDate date,

   CONSTRAINT PK_Project PRIMARY KEY (ProjectID),
   CONSTRAINT FK_Dept2 FOREIGN KEY(DepartmentName)
      REFERENCES DEPARTMENT(DepartmentName)
);



```

