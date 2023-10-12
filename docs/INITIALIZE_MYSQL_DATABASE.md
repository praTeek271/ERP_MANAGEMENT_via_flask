# Steps to Initialize MySQL Database

Setting up a MySQL database involves several steps, including creating a user, the database itself, and defining tables within it. Below are the essential steps to initialize a MySQL database:

1. **Create a MySQL User:**

   Use the following commands in a MySQL shell to create a user and grant privileges:

   ```sql
   mysql -u <username> -p 
   Enter password:

   mysql> CREATE USER 'dbms'@'localhost' IDENTIFIED BY 'justanothersecret';
   mysql> GRANT ALL PRIVILEGES ON *.* TO 'dbms'@'localhost';
   mysql> FLUSH PRIVILEGES;
   ```

   Example: Creating a user 'dbms' with privileges.

2. **Create a Database:**

   Within the MySQL shell, execute these commands to create a new database and select it:

   ```sql
   mysql> CREATE DATABASE erp;
   mysql> USE erp;
   ```

   Example: Creating a database named 'erp'.

3. **Create the `user` Table:**

   Define the structure of the `user` table using these MySQL commands:

   ```sql
   mysql> CREATE TABLE user (
      username VARCHAR(100) NOT NULL,
      password VARCHAR(100) NOT NULL,
      type ENUM('user', 'admin') NOT NULL,
      PRIMARY KEY(username)
   );
   mysql> INSERT INTO user
      VALUES ('Admin', 'Admin', 'admin');
   ```

   Example: Creating a table to store user information with an initial 'Admin' entry.

4. **Create the `profile` Table:**

   Similarly, create the `profile` table by executing these MySQL commands:

   ```sql
   mysql> CREATE TABLE profile (
      username VARCHAR(100) NOT NULL,
      name VARCHAR(100) NOT NULL,
      dob DATE,
      sex ENUM('Male', 'Female') NOT NULL,
      email VARCHAR(100),
      address VARCHAR(100),
      number VARCHAR(20),
      PRIMARY KEY(username)
   );
   mysql> INSERT INTO profile
      VALUES ('admin', 'Administrator God', '2017-04-15', 'Male', 'gurek15033@iiitd.ac.in', 'IIIT-Delhi, Okhla Estate III', '9910004979');
   ```

   Example: Creating a table to store user profiles with an initial 'admin' entry.

These steps outline how to initialize a MySQL database, create tables, and populate them with sample data. You can customize the table structures and data according to your specific requirements.