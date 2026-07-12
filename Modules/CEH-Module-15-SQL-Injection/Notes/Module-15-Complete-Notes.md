# Module 15 – SQL Injection

---

# Introduction to Databases

## Overview

A **database** is an organized collection of structured information that enables efficient storage, retrieval, modification, and management of data.

Modern organizations rely on databases to store and process large volumes of information for applications such as banking, e-commerce, healthcare, education, social media, and enterprise systems.

Examples of stored data include:

- Customer information
- User accounts
- Orders
- Payment records
- Employee details
- Inventory
- Medical records

---

# What is a Database Management System (DBMS)?

A **Database Management System (DBMS)** is software that allows users and applications to create, manage, retrieve, update, and delete data stored in databases.

A DBMS acts as the interface between applications and the underlying database.

Responsibilities include:

- Data storage
- Data retrieval
- Data modification
- User management
- Security
- Backup and recovery
- Concurrency control

---

# DBMS vs RDBMS

## DBMS

A DBMS stores data but may not necessarily organize it into related tables.

Characteristics:

- Single-user support (typically)
- Less structured relationships
- Simpler architecture
- Suitable for smaller applications

Examples:

- dBase
- FoxPro

---

## RDBMS (Relational Database Management System)

An RDBMS stores data in **tables** consisting of rows and columns.

Relationships between tables are maintained using keys.

Characteristics:

- Table-based storage
- Supports relationships
- ACID compliance
- Multi-user support
- Better security
- High scalability

Examples:

- MySQL
- PostgreSQL
- Oracle Database
- Microsoft SQL Server
- MariaDB

---

# Advantages of RDBMS

- Data consistency
- Reduced redundancy
- Improved integrity
- Faster querying
- Better scalability
- Strong security
- Easier maintenance

---

# Common Database Components

## Table

A table stores related information in rows and columns.

Example:

| Employee ID | Name | Department |
|------------|------|------------|
| 101 | Alice | HR |
| 102 | Bob | IT |

---

## Row (Record)

A row represents one complete record.

Example:

```
101 | Alice | HR
```

---

## Column (Field)

A column represents a specific attribute.

Examples:

- Name
- Email
- Salary
- Department

---

## Primary Key

A Primary Key uniquely identifies each record in a table.

Characteristics:

- Unique
- Cannot be NULL
- One Primary Key per table

Example:

```
Employee_ID
```

---

## Foreign Key

A Foreign Key creates a relationship between two tables.

Benefits:

- Maintains referential integrity
- Reduces data duplication
- Links related information

---

# Database Architecture

A typical web application communicates with a database through the application server.

```
User
   │
Browser
   │
HTTP/HTTPS
   │
Web Server
   │
Application Server
   │
Database Server
```

The application server receives user requests and sends SQL queries to the database server.

---

# Structured Query Language (SQL)

SQL (**Structured Query Language**) is the standard language used to communicate with relational databases.

SQL allows users to:

- Create databases
- Create tables
- Retrieve records
- Insert records
- Update records
- Delete records
- Manage permissions

---

# SQL Categories

## DDL (Data Definition Language)

Used to define database structure.

Common commands:

- CREATE
- ALTER
- DROP
- TRUNCATE

---

## DML (Data Manipulation Language)

Used to manipulate data.

Common commands:

- INSERT
- UPDATE
- DELETE

---

## DQL (Data Query Language)

Used to retrieve information.

Command:

- SELECT

---

## DCL (Data Control Language)

Controls user permissions.

Commands:

- GRANT
- REVOKE

---

## TCL (Transaction Control Language)

Manages database transactions.

Commands:

- COMMIT
- ROLLBACK
- SAVEPOINT

---

# CRUD Operations

Most applications perform four basic operations:

| Operation | SQL Command |
|-----------|-------------|
| Create | INSERT |
| Read | SELECT |
| Update | UPDATE |
| Delete | DELETE |

These operations are collectively known as **CRUD**.

---

# Common Database Servers

### MySQL

- Open source
- Widely used in web applications
- Popular with PHP applications

---

### MariaDB

- Community-driven fork of MySQL
- High compatibility with MySQL

---

### PostgreSQL

- Open-source
- Advanced SQL features
- High reliability

---

### Microsoft SQL Server

- Enterprise database by Microsoft
- Common in Windows environments

---

### Oracle Database

- Enterprise-grade RDBMS
- Widely used in large organizations

---

### SQLite

- Lightweight database
- File-based
- Common in mobile and embedded applications

---

# Why Databases Are Targeted

Attackers target databases because they often contain:

- Personally Identifiable Information (PII)
- Login credentials
- Financial records
- Business data
- Customer information
- Intellectual property

Compromising a database can have significant business and legal consequences.

---

# Security Goals

Database security aims to ensure:

- Confidentiality
- Integrity
- Availability
- Authentication
- Authorization
- Accountability

---

# CEH Exam Tips

Remember:

- A DBMS manages data storage and retrieval.
- An RDBMS stores data in related tables.
- SQL is the standard language for relational databases.
- CRUD operations are Create, Read, Update, and Delete.
- Primary Keys uniquely identify records.
- Foreign Keys establish relationships between tables.
- Databases are valuable targets because they store sensitive information.

---

# Key Takeaways

- Databases are essential components of modern web applications.
- RDBMS platforms organize data into related tables using SQL.
- Understanding database fundamentals is necessary before learning SQL Injection techniques and database security.

---

# SQL Fundamentals

## Overview

Structured Query Language (SQL) is the standard language used to communicate with relational databases.

Applications use SQL to:

- Store information
- Retrieve records
- Update existing data
- Delete records
- Manage users and permissions

Most modern web applications interact with databases using SQL queries generated by the backend application.

---

# SQL Query Execution Process

A typical web application processes requests as follows:

```
User
   │
Login Form
   │
Application Server
   │
SQL Query
   │
Database Server
   │
Query Result
   │
Application
   │
User
```

The application receives user input, generates an SQL query, sends it to the database, and displays the result.

---

# Common SQL Statements

## SELECT

Retrieves information from a database table.

Purpose:

- View records
- Search data
- Generate reports

---

## INSERT

Adds new records.

Common uses:

- User registration
- Creating orders
- Adding products

---

## UPDATE

Modifies existing records.

Examples:

- Changing passwords
- Updating customer information
- Editing profiles

---

## DELETE

Removes records from a table.

Examples:

- Deleting inactive users
- Removing obsolete records

---

## CREATE

Creates new database objects.

Examples:

- Database
- Table
- View
- Index

---

## ALTER

Modifies an existing database object.

Examples:

- Add column
- Rename column
- Change data type

---

## DROP

Removes database objects permanently.

Examples:

- Table
- Database
- View

---

# SQL Queries in Web Applications

Almost every web application performs SQL queries behind the scenes.

Examples include:

- User login
- Search functionality
- Shopping cart
- Online banking
- Student portals
- Employee management systems

---

# Authentication Using Databases

Most applications authenticate users by verifying credentials stored in a database.

Typical process:

1. User enters credentials.
2. Application validates the input.
3. Database checks stored information.
4. If valid, access is granted.
5. Otherwise, access is denied.

---

# User Input and SQL Queries

Applications frequently accept user input through:

- Login forms
- Search boxes
- Contact forms
- Registration forms
- URL parameters
- Cookies
- HTTP headers
- API requests

Improper handling of this input may introduce security vulnerabilities.

---

# What is SQL Injection?

SQL Injection (SQLi) is a web application vulnerability that occurs when an application improperly processes untrusted input before interacting with a database.

Instead of treating user input purely as data, the application may incorrectly allow it to influence the SQL query.

This can affect the application's intended behavior and potentially expose or manipulate database information.

---

# Why SQL Injection Occurs

SQL Injection commonly results from:

- Improper input validation
- Dynamic SQL query construction
- Insecure coding practices
- Weak server-side validation
- Poor application design

---

# Applications Commonly Affected

Potential targets include:

- Login portals
- E-commerce websites
- Banking applications
- Government portals
- Hospital management systems
- Student information systems
- Content Management Systems (CMS)

---

# Impact of SQL Injection

If left unaddressed, SQL Injection may lead to:

- Unauthorized access
- Disclosure of sensitive information
- Modification of database records
- Data loss
- Authentication bypass
- Business disruption
- Regulatory compliance issues

---

# Secure Development Principles

To reduce SQL Injection risk, developers should:

- Validate all user input
- Use parameterized queries
- Implement prepared statements
- Apply least privilege
- Avoid dynamic SQL whenever possible
- Follow secure coding standards
- Perform security testing

---

# Database Security Controls

Organizations should implement:

- Strong authentication
- Role-Based Access Control (RBAC)
- Database encryption
- Patch management
- Secure configuration
- Logging and monitoring
- Database activity monitoring
- Regular security assessments

---

# SQL Injection in the OWASP Top 10

Injection remains one of the most significant web application security risks.

Modern secure development practices focus on:

- Input validation
- Secure coding
- Parameterized queries
- Least privilege
- Continuous testing

---

# Blue Team Perspective

Security teams should monitor for:

- Abnormal database activity
- Unexpected application errors
- Authentication anomalies
- Unusual database queries
- Excessive failed requests
- Suspicious API requests
- Unexpected privilege changes

---

# CEH Exam Tips

Remember:

- SQL is used to communicate with relational databases.
- SQL Injection occurs because applications improperly process untrusted input.
- Login forms are common locations where SQL Injection vulnerabilities may occur.
- Input validation and parameterized queries significantly reduce SQL Injection risk.
- SQL Injection remains one of the most important web application vulnerabilities.

---

# Key Takeaways

- SQL is the standard language for relational databases.
- Web applications rely on SQL to store and retrieve information.
- SQL Injection results from insecure handling of user input.
- Secure coding, input validation, and proper database security controls help protect applications from SQL Injection vulnerabilities.

---

# Types of SQL Injection

## Overview

SQL Injection vulnerabilities can appear in different forms depending on how an application processes user input and how the database responds.

Understanding these categories helps security professionals identify weaknesses, perform secure code reviews, and implement effective defensive controls.

---

# SQL Injection Classification

The major categories include:

- In-band SQL Injection
- Error-based SQL Injection
- Union-based SQL Injection
- Blind SQL Injection
- Boolean-based Blind SQL Injection
- Time-based Blind SQL Injection
- Out-of-band SQL Injection
- Second-order SQL Injection

---

# In-Band SQL Injection

## Overview

In-band SQL Injection is the most common category.

The attacker interacts with the application and receives results through the same communication channel used to send the request.

Characteristics:

- Single communication channel
- Direct application response
- Easier to identify during security testing

---

# Error-Based SQL Injection

## Overview

Error-based SQL Injection relies on database error messages that unintentionally reveal information about the application's database.

Possible information disclosed:

- Database type
- Table names
- Column names
- Query structure
- Database version

### Defensive Controls

- Disable verbose error messages
- Implement secure exception handling
- Log detailed errors internally
- Display generic errors to users

---

# Union-Based SQL Injection

## Overview

Union-based SQL Injection occurs when application queries combine results from multiple database queries.

If applications fail to validate input securely, unintended information may be returned.

### Defensive Controls

- Parameterized queries
- Prepared statements
- Input validation
- Least privilege
- Secure coding practices

---

# Blind SQL Injection

## Overview

Blind SQL Injection occurs when applications do not display database errors or query results directly.

Although no detailed database information is returned, application behavior may still indicate whether a query executed successfully.

Characteristics:

- No visible database errors
- More difficult to detect
- Requires careful security testing

---

# Boolean-Based Blind SQL Injection

## Overview

The application's response changes depending on whether a condition evaluates as true or false.

The database itself remains hidden, but differences in application behavior may reveal useful information.

### Defensive Controls

- Server-side validation
- Parameterized queries
- Secure coding
- Consistent application responses

---

# Time-Based Blind SQL Injection

## Overview

Instead of relying on application output, this technique observes differences in application response time.

Unexpected timing behavior may indicate that user input is influencing database queries.

### Defensive Controls

- Prepared statements
- Query optimization
- Input validation
- Database activity monitoring
- Logging and alerting

---

# Out-of-Band SQL Injection

## Overview

Out-of-band SQL Injection relies on alternative communication channels rather than the application's normal response.

This category is less common and generally depends on specific database capabilities and network conditions.

### Defensive Controls

- Restrict outbound connectivity
- Monitor unusual network traffic
- Apply least privilege
- Disable unnecessary database features

---

# Second-Order SQL Injection

## Overview

In second-order SQL Injection, malicious input is stored safely at first but later reused by the application in an unsafe manner.

This makes detection more difficult because the vulnerability appears during later processing rather than at the initial input stage.

### Defensive Controls

- Validate data during both input and output
- Use parameterized queries everywhere
- Review stored data processing
- Conduct secure code reviews

---

# Comparison of SQL Injection Types

| Type | Direct Response | Typical Characteristic |
|------|-----------------|------------------------|
| In-Band | Yes | Uses the normal application response |
| Error-Based | Yes | Relies on verbose database errors |
| Union-Based | Yes | Combines query results |
| Blind | No | No direct database output |
| Boolean-Based | Limited | Response differs based on application behavior |
| Time-Based | No | Relies on timing differences |
| Out-of-Band | No | Uses alternative communication methods |
| Second-Order | Delayed | Stored input is processed later |

---

# Detection Methods

Security teams should perform:

- Secure code reviews
- Static Application Security Testing (SAST)
- Dynamic Application Security Testing (DAST)
- Interactive Application Security Testing (IAST)
- Software Composition Analysis (SCA)
- Vulnerability Assessments
- Penetration Testing in authorized environments

---

# Defensive Best Practices

Organizations should:

- Validate all user input
- Use prepared statements
- Implement parameterized queries
- Avoid dynamic SQL where possible
- Apply least privilege
- Secure database configurations
- Keep database software updated
- Monitor database activity
- Enable centralized logging
- Perform regular security assessments

---

# Blue Team Detection Opportunities

Monitor for:

- Repeated database errors
- Unexpected query failures
- Abnormal database activity
- Unusual application behavior
- Large numbers of failed requests
- Excessive database resource usage
- Unexpected outbound connections from database servers

---

# CEH Exam Tips

Remember:

- In-band SQL Injection is the most common category.
- Error-based SQL Injection relies on verbose error messages.
- Blind SQL Injection does not directly reveal database output.
- Time-based techniques rely on response timing.
- Second-order SQL Injection occurs when stored input is later processed insecurely.
- Prepared statements and parameterized queries are primary defenses.

---

# Key Takeaways

- SQL Injection vulnerabilities exist in multiple forms depending on how applications process user input.
- Understanding these categories helps security professionals identify risks and implement appropriate defensive controls.
- Secure coding, proper input validation, parameterized queries, continuous monitoring, and regular security testing significantly reduce SQL Injection risk.

---

# SQL Injection Prevention & Database Security

## Overview

Preventing SQL Injection is far more effective than attempting to detect or remediate attacks after deployment.

Secure web applications combine **secure coding practices**, **proper database security**, **input validation**, and **continuous monitoring** to minimize SQL Injection risks.

Security should be integrated throughout the **Secure Software Development Life Cycle (SSDLC).**

---

# Secure Software Development Life Cycle (SSDLC)

Security should be considered during every development phase.

```
Requirements
      │
Design
      │
Development
      │
Testing
      │
Deployment
      │
Maintenance
```

Security activities include:

- Security requirements
- Threat modeling
- Secure coding
- Code reviews
- Security testing
- Vulnerability management
- Continuous monitoring

---

# Input Validation

Applications should treat **all user input as untrusted**.

Sources of user input include:

- Login forms
- Search fields
- Registration forms
- URL parameters
- Cookies
- HTTP headers
- API requests
- Uploaded files

### Best Practices

- Validate all input
- Use allowlists where possible
- Enforce length restrictions
- Validate data types
- Perform server-side validation
- Reject unexpected input

---

# Parameterized Queries

Parameterized queries separate **user input** from the SQL statement.

Benefits:

- Prevent SQL query manipulation
- Improve code readability
- Reduce SQL Injection risk
- Recommended by OWASP

Parameterized queries are considered the preferred method for interacting with relational databases.

---

# Prepared Statements

Prepared statements predefine SQL queries before user data is supplied.

Advantages:

- Prevent SQL Injection
- Improve performance for repeated queries
- Separate code from data
- Supported by most modern programming languages

---

# Stored Procedures

Stored procedures are SQL routines stored inside the database.

Advantages:

- Centralized business logic
- Reduced application complexity
- Improved maintainability

Important:

Stored procedures improve security only when implemented securely. Poorly designed procedures can still introduce vulnerabilities.

---

# Principle of Least Privilege

Applications should connect to databases using accounts with only the permissions required.

Avoid:

- Administrative database accounts
- Excessive privileges
- Shared privileged accounts

Benefits:

- Limits attacker capabilities
- Reduces impact of compromised applications
- Improves accountability

---

# Secure Error Handling

Applications should never expose detailed database errors to users.

Instead:

- Display generic error messages
- Log detailed errors internally
- Protect log integrity
- Review logs regularly

---

# Database Hardening

Database servers should be securely configured.

Recommendations:

- Remove unused accounts
- Disable unnecessary services
- Change default credentials
- Restrict remote access
- Enable encryption
- Apply security patches
- Configure secure authentication
- Review permissions regularly

---

# Patch Management

Database software should always remain up to date.

Update:

- Database server
- Operating system
- Database drivers
- Client libraries
- Framework dependencies

Regular patching reduces exposure to known vulnerabilities.

---

# Logging and Monitoring

Databases should log important security events.

Examples:

- Authentication attempts
- Failed logins
- Administrative actions
- Privilege changes
- Query failures
- Configuration changes
- Security alerts

Recommendations:

- Centralize logs
- Protect log integrity
- Synchronize timestamps
- Configure alerting
- Review logs regularly

---

# Database Activity Monitoring (DAM)

Database Activity Monitoring solutions help organizations observe database activity in real time.

Benefits:

- Detect unusual behavior
- Identify unauthorized access
- Improve compliance
- Support incident response

---

# Web Application Firewall (WAF)

A Web Application Firewall helps inspect HTTP/HTTPS traffic before it reaches the application.

Benefits:

- Filters malicious requests
- Blocks known attack patterns
- Reduces exposure to common web attacks
- Provides additional visibility

Examples:

- ModSecurity
- Cloudflare WAF
- AWS WAF
- Azure Web Application Firewall

---

# Security Testing

Organizations should perform regular security assessments.

Common testing methods include:

- Secure Code Review
- Static Application Security Testing (SAST)
- Dynamic Application Security Testing (DAST)
- Interactive Application Security Testing (IAST)
- Software Composition Analysis (SCA)
- Vulnerability Assessment
- Penetration Testing (authorized environments only)

---

# Backup and Recovery

Protect database availability by maintaining secure backups.

Best Practices:

- Encrypt backups
- Test restoration procedures
- Store backups securely
- Maintain offline or immutable copies

---

# Incident Response

Database security incidents should follow a structured response process.

Typical phases:

1. Preparation
2. Detection
3. Analysis
4. Containment
5. Eradication
6. Recovery
7. Lessons Learned

---

# Secure Coding Checklist

Developers should:

- Validate all input
- Use parameterized queries
- Use prepared statements
- Apply least privilege
- Handle errors securely
- Avoid dynamic SQL whenever possible
- Keep dependencies updated
- Perform security testing before deployment

---

# Blue Team Detection Opportunities

Monitor for:

- Repeated database authentication failures
- Unexpected database queries
- Privilege escalation attempts
- Abnormal database activity
- Large data exports
- Unauthorized configuration changes
- Excessive failed application requests
- Unusual outbound network connections

---

# CEH Exam Tips

Remember:

- Input validation alone is not sufficient.
- Parameterized queries are the primary defense against SQL Injection.
- Prepared statements separate code from user input.
- Least privilege reduces the impact of compromise.
- Secure error handling prevents unnecessary information disclosure.
- Logging and monitoring improve incident detection.
- Database hardening reduces attack surface.

---

# Key Takeaways

- SQL Injection prevention requires secure coding, secure database configuration, proper authentication, least privilege, and continuous monitoring.
- Parameterized queries and prepared statements are the recommended defenses against SQL Injection.
- Database security should be integrated throughout the Secure Software Development Life Cycle (SSDLC) rather than treated as an afterthought.

---

# MITRE ATT&CK Mapping, Blue Team Perspective & Module Summary

## Overview

The **MITRE ATT&CK Framework** is a globally recognized knowledge base that documents adversary tactics, techniques, and procedures (TTPs) observed in real-world cyber attacks.

SQL Injection is commonly used as an **initial attack vector** against Internet-facing web applications and can enable attackers to access sensitive databases, escalate privileges, or compromise application functionality.

Understanding how SQL Injection maps to MITRE ATT&CK helps defenders improve detection, prevention, and incident response.

---

# ATT&CK Tactics Relevant to SQL Injection

| Tactic | Relevance |
|---------|-----------|
| Initial Access | Internet-facing web applications may be targeted through SQL Injection vulnerabilities. |
| Discovery | Attackers may gather information about databases, tables, or application structure. |
| Credential Access | Weakly protected databases may expose authentication information. |
| Collection | Sensitive application or business data may be collected. |
| Exfiltration | Stolen information may be transferred outside the organization. |
| Defense Evasion | Attackers may attempt to bypass security controls or logging mechanisms. |

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Repeated database errors
- Unusual SQL query patterns
- Excessive failed login attempts
- Large or unexpected database exports
- Unauthorized privilege changes
- Unexpected database connections
- Abnormal API requests
- High-frequency requests to login or search pages
- Database performance anomalies
- Suspicious outbound network traffic

---

# Database Security Controls

Organizations should implement multiple layers of defense.

| Security Control | Purpose |
|------------------|---------|
| Parameterized Queries | Separate user input from SQL statements |
| Prepared Statements | Prevent SQL Injection through safe query execution |
| Input Validation | Reject unexpected or malformed input |
| Role-Based Access Control (RBAC) | Restrict user permissions |
| Principle of Least Privilege | Limit database account permissions |
| Database Encryption | Protect sensitive data |
| Patch Management | Address known vulnerabilities |
| Database Activity Monitoring (DAM) | Monitor real-time database activity |
| Web Application Firewall (WAF) | Filter malicious HTTP/HTTPS requests |
| SIEM | Centralized logging and security monitoring |

---

# Secure Development Checklist

Before deploying an application, verify that:

- User input is validated
- Parameterized queries are used
- Prepared statements are implemented
- Dynamic SQL is minimized
- Database accounts use least privilege
- Database software is fully patched
- Secure error handling is configured
- Sensitive data is encrypted
- Logging and monitoring are enabled
- Security testing has been completed

---

# CEH Revision Notes

Remember:

- SQL is the standard language for relational databases.
- SQL Injection occurs when applications improperly process untrusted input.
- Injection remains one of the most critical web application security risks.
- Parameterized queries are the preferred defense against SQL Injection.
- Prepared statements separate code from user input.
- Secure error handling prevents information disclosure.
- Least privilege limits attacker impact.
- Continuous monitoring improves detection and response.

---

# Interview Tips

Be prepared to explain:

- What SQL Injection is.
- Why SQL Injection occurs.
- Common SQL Injection categories.
- The difference between parameterized queries and prepared statements.
- Why input validation alone is not enough.
- How least privilege protects databases.
- The purpose of database activity monitoring.
- How a Web Application Firewall (WAF) helps protect web applications.
- The importance of secure coding and SSDLC.
- How logging supports incident response.

---

# Real-World Applications

Knowledge from this module is valuable for roles such as:

- SOC Analyst
- VAPT Analyst
- Penetration Tester
- Application Security Engineer
- Security Consultant
- Security Auditor
- DevSecOps Engineer

---

# Key Takeaways

- SQL Injection remains one of the most significant web application security risks.
- Most SQL Injection vulnerabilities result from insecure handling of user input.
- Secure coding, parameterized queries, prepared statements, least privilege, and database hardening significantly reduce risk.
- Continuous monitoring, logging, and layered security controls improve an organization's ability to detect and respond to attacks.
- Understanding SQL Injection is essential for ethical hackers, defenders, developers, and application security professionals.

---

# Module Summary

Module 15 introduced relational databases, SQL fundamentals, SQL Injection concepts, common SQL Injection categories, secure coding practices, database hardening, defensive security controls, MITRE ATT&CK mapping, and Blue Team detection strategies.

These concepts provide a strong foundation for CEH certification, secure web application development, vulnerability assessments, penetration testing, and application security.

