# 💉 SQL Injection Concepts
This section discusses the basic concepts of SQL injection attacks and their intensity. It starts with an introduction to SQL injection and the basics required to understand SQL injection attacks, followed by some examples of such attacks.

---
## What is SQL Injection? 
Structured Query Language (SQL) is a textual language used by a database server. SQL commands used to perform operations on the database include **INSERT**, **SELECT**, **UPDATE**, and **DELETE**. These commands are used to manipulate data in the database server. 

SQL injection is a common web application vulnerability that occurs when developers use sequential SQL commands with user-supplied input without proper validation or sanitization. Attackers take advantage of this weakness by injecting malicious SQL code into input fields, such as login forms or search boxes, which the application then sends to the backend database for execution. This allows attackers to bypass authentication, gain unauthorized access, or directly extract sensitive information from the database.

### Why Bother about SQL Injection? 
SQL injection is a major issue for all database-driven websites. An attack can be attempted on any normal website or software package based on how it is used and how it processes user-supplied data. SQL injection can be used to implement the following attacks:
- **Authentication Bypass:** Using this attack, an attacker logs onto an application without providing a valid username and password, and gains administrative privileges.
- **Authorization Bypass:** Using this attack, an attacker alters authorization information stored in the database by exploiting an SQL injection vulnerability.
- **Information Disclosure:** Using this attack, an attacker obtains sensitive information that is stored in the database.
- **Compromised Data Integrity:** Using this attack, an attacker defaces a web page, inserts malicious content into web pages, or alters the contents of a database.
- **Compromised Availability of Data:** Using this attack, an attacker deletes the database information, delete logs, or audit information stored in a database.
- **Remote Code Execution:** Using this attack, an attacker compromises the host OS.

---
## SQL Injection and Server-side Technologies 
Server-side technologies like ASP.NET, PHP, JSP, and others make it easy to build dynamic, data-driven applications that interact with databases such as MySQL, Oracle, or SQL Server. However, if secure coding practices are ignored, these applications can become vulnerable to SQL injection. SQL injection does not target the software itself but exploits poorly written code to manipulate database queries, allowing attackers to access or modify sensitive data.

---
## Understanding HTTP POST Request 
An HTTP POST request is used to send data from the client to the web server through the request body, making it more secure than GET and suitable for larger amounts of data. It is commonly used for actions like submitting login forms, where credentials are sent to the server for validation. For example, when a user logs in, the request may carry a query such as:
```sql
select * from Users where (username = 'smith' and password = 'simpson');
```
which the server processes to check the user’s details.

<p align="center">
  <img width="653" height="494" alt="image" src="https://github.com/user-attachments/assets/8a750d6d-790d-4922-8437-de1f29209159" />
</p>

---
## Understanding Normal SQL Query 
A normal SQL query is a command used to interact with a database, such as retrieving, inserting, updating, or deleting data. Queries start with keywords like **SELECT**, **UPDATE**, **CREATE**, or **DELETE**, and are often built from user input passed through an application. Once constructed, the query is executed on the server to perform the requested operation on the database.

The diagram below shows a typical SQL query. It is constructed with user-supplied values, and upon execution, it displays results from the database.

<p align="center">
  <img width="774" height="354" alt="image" src="https://github.com/user-attachments/assets/15343ddd-63dd-4bf4-a022-e2c034ce9254" />
</p>

---
## Understanding an SQL Injection Query 
SQL injection is a technique where attackers exploit the way an application handles user input in SQL queries. Instead of entering normal values, attackers inject malicious input that changes the logic of the query to gain unauthorized access to data. This happens when the application fails to properly validate or filter the input before passing it to the database.

For example, in a login form that takes a username and password, the attacker might enter a value like 
```
Username: Blah' or 1=1 --
Password: Pe***&4** 
```
in the username and password field. When this input is processed, the SQL query becomes:
```sql
SELECT Count(*) FROM Users WHERE UserName='Blah' or 1=1 --' AND Password='Pe***&4**';
```

In this query, the condition `or 1=1` always evaluates to true. As a result, the database returns a valid response even if the attacker does not provide the correct credentials. This allows unauthorized access without knowing a legitimate username and password.

The diagram below shows a typical SQL injection query. 

<p align="center">
  <img width="778" height="350" alt="image" src="https://github.com/user-attachments/assets/501bcdf2-c6f7-42ad-9723-abd56335d69a" />
</p>

---
## Understanding an SQL Injection Query—Code Analysis 
Code analysis or code review is the most effective technique for identifying vulnerabilities or flaws in the code. An attacker exploits the vulnerabilities found in the code to gain access to the database. An attacker logs into an account by the following process: 
1. A user enters a username and password that match a record in the user’s table
2. A dynamically generated SQL query is used to retrieve the number of matching rows
3. The user is then authenticated and redirected to the requested page
4. When the attacker enters `blah' or 1=1 --`, then the SQL query will look like
```sql
SELECT Count(*) FROM Users WHERE UserName='blah' Or 1=1 --' AND Password='Pe***&4**'
```
5. A pair of hyphens indicate the beginning of a comment in SQL; therefore, the query simply becomes
```sql
SELECT Count(*) FROM Users WHERE UserName='blah' Or 1=1
string strQry = "SELECT Count(*) FROM Users WHERE UserName='" + txtUser.Text + "' AND Password='" + txtPassword.Text + "'";
```

---
## Example of a Web Application Vulnerable to SQL Injection: BadProductList.aspx
BadProductList.aspx is an example of a web application that is highly vulnerable to SQL injection because it directly uses user input from the `txtFilter` textbox to build SQL queries without proper validation or sanitization. This allows attackers to manipulate the query and gain unauthorized access to sensitive information stored in the database.

For instance, by entering a crafted input such as:
```sql
UNION SELECT id, name, '', 0 FROM sysobjects WHERE xtype ='U' --
```
the attacker can retrieve the names of user-created tables from the system table `sysobjects`. This reveals valuable schema information, including the existence of a `Users` table. With this knowledge, the attacker can refine the attack further and extract sensitive data such as usernames and passwords by using a query like:
```sql
UNION SELECT 0, UserName, Password, 0 FROM Users --
```
This query takes advantage of the UNION statement, which merges the results of two queries, and exposes the login credentials stored in the database.

Because the page is dynamically constructing queries from user input, attackers could not only read confidential information but also manipulate or delete data, create new accounts, or damage the entire database. This highlights the danger of insecure coding practices in web applications. Without input validation, parameterized queries, or stored procedures, the application becomes an easy target for SQL injection, which is one of the most critical threats in web application security.

<p align="center">
  <img width="573" height="443" alt="image" src="https://github.com/user-attachments/assets/387cc6cf-25e2-442f-a4a3-82e626e6379e" />
</p>

---
## Example of a Web Application Vulnerable to SQL Injection: Attack Analysis 
Most websites provide search to enable users to find a specific product or service quickly. A separate Search field is maintained on the website in an area that is easily viewable. As with any other input field, attackers target this field to perform SQL injection attacks. An attacker enters specific input values in the Search field to perform an SQL injection attack.

<p align="center">
  <img width="825" height="365" alt="image" src="https://github.com/user-attachments/assets/62f0d83e-d73b-4af6-a98b-14357ff8c106" />
</p>

---
## Examples of SQL Injection 
An SQL injection query exploits the normal execution of SQL. The attacker uses various SQL commands to modify the values in the database.

<p align="center">
  <img width="741" height="350" alt="image" src="https://github.com/user-attachments/assets/f05d85a2-b9bb-4c45-8d47-7d684664b7a5" />
</p>

The following table lists some examples of SQL injection attacks: 

| Example | Attacker SQL Query | SQL Query Executed |
|---|---|---|
| **Updating Table** | `blah'; UPDATE jb-customers SET jb-email = 'info@certifiedhacker.com' WHERE email ='jason@springfield.com; --` | `SELECT jb-email, jb-passwd, jb-login_id, jb-last_name FROM members WHERE jb-email = 'blah'; UPDATE jb-customers SET jb-email = 'info@certifiedhacker.com' WHERE email ='jason@springfield.com; --';` |
| **Adding New Records** | `blah'; INSERT INTO jb-customers ('jb-email','jb-passwd','jb-login_id','jb-last_name') VALUES ('jason@springfield.com','hello','jason','jason springfield');-` | `SELECT jb-email, jb-passwd, jb-login_id, jb-last_name FROM members WHERE email = 'blah'; INSERT INTO jb-customers ('jb-email','jb-passwd','jb-login_id','jb-last_name') VALUES ('jason@springfield.com','hello','jason', ‘jason springfield');--';` |
| **Identifying the Table Name** | `blah' AND 1=(SELECT COUNT(*) FROM mytable); --` <br> Note: You will need to guess table names here | `SELECT jb-email, jb-passwd, jb-login_id, jb-last_name FROM table WHERE jb-email = 'blah' AND 1=(SELECT COUNT(*) FROM mytable); --';` |
| **Deleting a Table** | `blah'; DROP TABLE Creditcard; --` | `SELECT jb-email, jb-passwd, jb-login_id, jb-last_name FROM members WHERE jb-email = 'blah'; DROP TABLE Creditcard; --';` |
| **Returning More Data** | `OR 1=1` | `SELECT * FROM User_Data WHERE Email_ID = 'blah' OR 1=1` |
