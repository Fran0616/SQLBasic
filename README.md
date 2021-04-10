# SQLBasic

Structured Query Language (SQL)
=

SQL is industry stadard languge for defining, manipulating, and retriving the data in a database. It was develop at IBM by Donald Chamberlin and Raymond Boyce in the early 1970s. SQL is not a complete programming language but a data sub language. It can be divided into two categories DDL, DML. Data definition languge (DDL) statments used for creatin tables, relationships, and other strutres. Dadta Manipulation (DML) statemment used for quiries and data modification. Selecet, intert, Delee, and update. 

CREATE TABLE statement is ised for defining the scheme of the database. It consist of three parts. Column name, data type, and constraints. 

ie: 
```
CREATE TABLE TableNameHere(
column1 datatype constrain,
column2 datatype constrain,
CONSTRAIN PRIMARY KEY (column1),
 CONSTRAINT FOREIGN KEY(column2)
      REFERENCES SomeTableNameGoesHere(ColumnFromTable)

```
