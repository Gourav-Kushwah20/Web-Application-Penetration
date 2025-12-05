# 🧠 Types-of-SQL-Injections (SQLi)

## 🔹 Types of SQL Injections (SQLi)

SQL Injection (SQLi) is one of the most common web security vulnerabilities that allows attackers to interfere with queries made to a database. Different types of SQL injections depend on how attackers extract or manipulate information.

---

## 💥 In-band SQLi

In-band SQLi is the **most straightforward and frequent technique**.
The attacker uses the same communication channel to both inject malicious SQL queries and retrieve results.

### ⚠️ Error-based SQLi

* Exploits database error messages to gain information about database structure.
* For example, attackers intentionally write invalid queries to reveal table names, column names, or data types from verbose errors.
* Effective if the database is configured to display detailed error messages.

### 🔗 Union-based SQLi

* Exploits the `UNION` operator to combine results of legitimate queries with malicious `SELECT` statements.
* Example: retrieving usernames, passwords, or emails in the same HTTP response.
* Relies heavily on being able to guess the correct number and types of columns in the query.

---

## 🕵️ Blind SQLi

Blind SQLi is used when the database does not return error messages or direct query outputs.
Attackers must infer information indirectly from the application's behavior, making it **slower but stealthier**.

### 🧩 Boolean-based SQLi

* Attackers craft queries so the application responds differently depending on whether a condition is **TRUE** or **FALSE**.
* Example: a page might display different content if a query condition is true (data exists) versus false (no data).
* Information is extracted one piece at a time.

### ⏱️ Time-based SQLi

* Exploits SQL functions that delay execution (e.g., `SLEEP()` or `WAITFOR DELAY`).
* Attackers detect whether a query result is true or false by measuring server response time.
* Useful when no content differences appear in responses but timing can still be measured.

---
## Out-of-band SQLi
Out-of-band-SQli is used when in-band and blind SQLi are not possible ,often due to unstable server or limited query feedback.

* Relies on database features that allow generating `DNS or HTTP requests` to external servers.
* Data is exfiltrated via these requests to attacker-controlled systems.
* More rare,but effective with databases that allow outbound connections(e.g., Microsoft SQL server with `xp_dirtree,`Oracle with `UTL_HTTP`).