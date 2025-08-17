# 💉 SQL Injection Concepts
This section discusses the basic concepts of SQL injection attacks and their intensity. It starts with an introduction to SQL injection and the basics required to understand SQL injection attacks, followed by some examples of such attacks.

---
## What is SQL Injection? 
Structured Query Language (SQL) is a textual language used by a database server. SQL commands used to perform operations on the database include **INSERT**, **SELECT**, **UPDATE**, and **DELETE**. These commands are used to manipulate data in the database server. 

SQL injection is a common web application vulnerability that occurs when developers use sequential SQL commands with user-supplied input without proper validation or sanitization. Attackers take advantage of this weakness by injecting malicious SQL code into input fields, such as login forms or search boxes, which the application then sends to the backend database for execution. This allows attackers to bypass authentication, gain unauthorized access, or directly extract sensitive information from the database.

### Why Bother about SQL Injection? 
