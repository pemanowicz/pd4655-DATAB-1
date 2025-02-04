# pd4655-DATAB-1

**Schema (MySQL v5.7)**

    CREATE TABLE patients (
        id INT PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        date_of_birth DATE NOT NULL,
        email VARCHAR(255) UNIQUE,
        phone_number VARCHAR(15),
        weight DECIMAL(5,2),
        height INT
    );
    

---

**Query #1**

    INSERT INTO patients (id, name, date_of_birth, email, phone_number, weight, height)
    VALUES 
    (1, 'John Doe', '1985-06-15', 'john.doe@gmail.com', '1234567890', 72.50, 180),
    (2, 'Jane Smith', '1990-03-20', 'jane.smith@gmail.com', '987654321', 60.00, 165),
    (3, 'Maria Garcia', '1978-12-05', 'NULL', '1122334455', 68.00, 170),
    (4, 'James Brown', '2000-07-15', 'james.brown@yahoo.com', '5566778899', 80.25, 175),
    (5, 'Emily Davis', '1995-02-10', 'emily.davis@otlook.com', '6677889900', 55.50, 160);

There are no results to be displayed.

---
**Query #2**

    
    
    SELECT * FROM patients;

| id  | name         | date_of_birth | email                  | phone_number | weight | height |
| --- | ------------ | ------------- | ---------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com     | 1234567890   | 72.50  | 180    |
| 2   | Jane Smith   | 1990-03-20    | jane.smith@gmail.com   | 987654321    | 60.00  | 165    |
| 3   | Maria Garcia | 1978-12-05    | NULL                   | 1122334455   | 68.00  | 170    |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com  | 5566778899   | 80.25  | 175    |
| 5   | Emily Davis  | 1995-02-10    | emily.davis@otlook.com | 6677889900   | 55.50  | 160    |

---
**Query #3**

    
    SELECT * FROM patients WHERE weight > 65;

| id  | name         | date_of_birth | email                 | phone_number | weight | height |
| --- | ------------ | ------------- | --------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com    | 1234567890   | 72.50  | 180    |
| 3   | Maria Garcia | 1978-12-05    | NULL                  | 1122334455   | 68.00  | 170    |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com | 5566778899   | 80.25  | 175    |

---
**Query #4**

    
    SELECT * FROM patients ORDER BY height DESC;

| id  | name         | date_of_birth | email                  | phone_number | weight | height |
| --- | ------------ | ------------- | ---------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com     | 1234567890   | 72.50  | 180    |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com  | 5566778899   | 80.25  | 175    |
| 3   | Maria Garcia | 1978-12-05    | NULL                   | 1122334455   | 68.00  | 170    |
| 2   | Jane Smith   | 1990-03-20    | jane.smith@gmail.com   | 987654321    | 60.00  | 165    |
| 5   | Emily Davis  | 1995-02-10    | emily.davis@otlook.com | 6677889900   | 55.50  | 160    |

---
**Schema (MySQL v5.7)**

    CREATE TABLE patients (
        id INT PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        date_of_birth DATE NOT NULL,
        email VARCHAR(255) UNIQUE,
        phone_number VARCHAR(15),
        weight DECIMAL(5,2),
        height INT
    );
    

---

**Query #1**

    INSERT INTO patients (id, name, date_of_birth, email, phone_number, weight, height)
    VALUES 
    (1, 'John Doe', '1985-06-15', 'john.doe@gmail.com', '1234567890', 72.50, 180),
    (2, 'Jane Smith', '1990-03-20', 'jane.smith@gmail.com', '987654321', 60.00, 165),
    (3, 'Maria Garcia', '1978-12-05', 'NULL', '1122334455', 68.00, 170),
    (4, 'James Brown', '2000-07-15', 'james.brown@yahoo.com', '5566778899', 80.25, 175),
    (5, 'Emily Davis', '1995-02-10', 'emily.davis@otlook.com', '6677889900', 55.50, 160);

There are no results to be displayed.

---
**Query #2**

    
    
    UPDATE patients 
    SET email = 'john.updated@gmail.com' 
    WHERE name = 'John Doe';

There are no results to be displayed.

---
**Query #3**

    
    
    DELETE FROM patients WHERE id = 3;

There are no results to be displayed.

---
**Query #4**

    
    
    ALTER TABLE patients ADD blood_type CHAR(3);

There are no results to be displayed.

---
**Query #5**

    
    
    DESCRIBE patients;

| Field         | Type         | Null | Key | Default | Extra |
| ------------- | ------------ | ---- | --- | ------- | ----- |
| id            | int(11)      | NO   | PRI |         |       |
| name          | varchar(255) | NO   |     |         |       |
| date_of_birth | date         | NO   |     |         |       |
| email         | varchar(255) | YES  | UNI |         |       |
| phone_number  | varchar(15)  | YES  |     |         |       |
| weight        | decimal(5,2) | YES  |     |         |       |
| height        | int(11)      | YES  |     |         |       |
| blood_type    | char(3)      | YES  |     |         |       |

---
**Query #6**

    
    
    UPDATE patients SET blood_type = 'O+' WHERE name = 'John Doe';

There are no results to be displayed.

---
**Query #7**

    
    UPDATE patients SET blood_type = 'AB+' WHERE name = 'Jane Smith';

There are no results to be displayed.

---
**Query #8**

    
    UPDATE patients SET blood_type = 'B+' WHERE name = 'Emily Davis';

There are no results to be displayed.

---
**Query #9**

    
    
    
    SELECT * FROM patients;

| id  | name        | date_of_birth | email                  | phone_number | weight | height | blood_type |
| --- | ----------- | ------------- | ---------------------- | ------------ | ------ | ------ | ---------- |
| 1   | John Doe    | 1985-06-15    | john.updated@gmail.com | 1234567890   | 72.50  | 180    | O+         |
| 2   | Jane Smith  | 1990-03-20    | jane.smith@gmail.com   | 987654321    | 60.00  | 165    | AB+        |
| 4   | James Brown | 2000-07-15    | james.brown@yahoo.com  | 5566778899   | 80.25  | 175    |            |
| 5   | Emily Davis | 1995-02-10    | emily.davis@otlook.com | 6677889900   | 55.50  | 160    | B+         |

---
**Query #10**

    
    
    SELECT * FROM patients ORDER BY id DESC LIMIT 2;

| id  | name        | date_of_birth | email                  | phone_number | weight | height | blood_type |
| --- | ----------- | ------------- | ---------------------- | ------------ | ------ | ------ | ---------- |
| 5   | Emily Davis | 1995-02-10    | emily.davis@otlook.com | 6677889900   | 55.50  | 160    | B+         |
| 4   | James Brown | 2000-07-15    | james.brown@yahoo.com  | 5566778899   | 80.25  | 175    |            |

---

[View on DB Fiddle](https://www.db-fiddle.com/)
[View on DB Fiddle](https://www.db-fiddle.com/)
