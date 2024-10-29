# Creating and Managing a Healthcare Database in SQL Server

## Objective

In this lab, the goal is to create and manage a simple healthcare database using SQL commands within Microsoft SQL Server Management Studio (SSMS). You will create five tables—Patient, Test, Treatment, Personnel, and Bed—and populate them with sample data. This lab emphasizes the use of SQL commands for table creation and data manipulation rather than the table designer tool in SSMS.

### Skills Learned
- Creating tables using SQL `CREATE TABLE` commands.
- Inserting data into tables using `INSERT INTO`.
- Querying data using `SELECT * FROM`.
- Understanding data types, constraints, and attributes in SQL.

### Tools Used
- Microsoft SQL Server Management Studio (SSMS)
- SQL Developer Server
- SQL commands: `CREATE TABLE`, `INSERT INTO`, `SELECT`

## Steps

### 1. Setting up the Environment
We began the lab by downloading Microsoft SQL Server Management Studio (SSMS) and connecting to a developer server. Once connected, we created a new database named **HealthcareDB**

![image](https://github.com/user-attachments/assets/9dff43c7-9f9b-48d1-a350-24b425c77e2a)

With the server connected and the databse named, we begin to create our first table.

Only issue is that the above image shows the table designer mode of SSMS and for the sake of this project we want to demonstrate SQL knowledge so we navigate to the left toolbar and click "New Query" which allows me to type the contents of my table

### 2. Creating the Table

I begin to create my first table by using the “CREATE TABLE (TABLE NAME)” Command
And input the characteristics

A key note is that for each characteristic I specify the acceptable MAXIMUM variable length to be inputted via the command ```VARCHAR(Number)```

Here is the code for the table, patient

![image](https://github.com/user-attachments/assets/3ae78dcb-4cb5-4b04-ba37-34f87f24bf21)

Next we create a table called test with the attributes of test_code (key), description and cost

Notable: cost is given a data type called DECIMAL(10,2) which is commonly used with financial values. (10,2) specifying two different things. 10 specifies the precision of the input or the total number of digits both to the right and left of the decimal and 2 specifies the scale which is how many digits are allowed after the decimal which is 2.
For description I gave the user the ability to place up to 300 characters 

![image](https://github.com/user-attachments/assets/745ffd3b-b839-41b7-9643-799170b1e6ce)

We follow the same process for the creation of the table, Treatment

![image](https://github.com/user-attachments/assets/9cfb323c-ace7-4aac-b770-f2aedda21ab1)

The creation of the Personnel table follows many of the same attributes witnessed in the patient table

![image](https://github.com/user-attachments/assets/eb339c82-6d49-4b5a-bf8d-c9cf010e684f)

And for the last table, bed, we input the attributes of bed_ID and description

![image](https://github.com/user-attachments/assets/0fb1ce5b-b5ec-40ed-ada8-ed95db60b1f3)

### 3. Inserting Data into the Tables

With this being done now we can begin inputting data into the tables

I used the command “INSERT INTO” followed by the table name and its attributes to begin inputting information. I listed the information in the same order I listed the attributes in the command

![image](https://github.com/user-attachments/assets/e46b7444-4359-4804-9017-e4bc53bd7979)

![image](https://github.com/user-attachments/assets/b92eb4c0-c0b3-440e-90c2-c3bfc546b379)

### 4. Querying the Data
After inserting data, we queried each table using the SELECT * FROM command to display all records. For example:
```SELECT * FROM Patient;```


![image](https://github.com/user-attachments/assets/aa913cd0-b56b-4afc-af18-eb3767501c42)

