# Web Application Fundamentals

## Overview

A web application is software that runs on a web server and is accessed through a web browser using HTTP or HTTPS.

Unlike traditional desktop applications, web applications do not require installation on the client's device. Users interact with them through a browser, while the application logic executes on the server.

Examples include:

- Gmail
- GitHub
- Amazon
- Facebook
- Microsoft 365
- Online Banking
- Netflix
- Student Portals

---

# Web Application vs Website

| Website | Web Application |
|----------|-----------------|
| Primarily provides information | Provides interactive services |
| Mostly static content | Dynamic content |
| Limited user interaction | Extensive user interaction |
| Usually no authentication | Authentication often required |
| Simpler architecture | More complex architecture |

---

# Web Application Architecture

A typical web application consists of four main components:

```
User
   │
   ▼
Web Browser
   │
HTTP / HTTPS
   │
   ▼
Web Server
   │
   ▼
Application Server
   │
   ▼
Database Server
```

### 1. Client (Browser)

The client is the user's web browser.

Responsibilities:

- Sending HTTP/HTTPS requests
- Rendering web pages
- Executing JavaScript
- Managing cookies
- Displaying application content

Examples:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

---

### 2. Web Server

The web server receives requests from clients and serves web content or forwards requests to the application server.

Examples:

- Apache HTTP Server
- Nginx
- Microsoft IIS

---

### 3. Application Server

The application server processes business logic.

Responsibilities include:

- Authentication
- Authorization
- Session management
- Processing user requests
- Database communication

Common technologies:

- PHP
- ASP.NET
- Java
- Python
- Node.js

---

### 4. Database Server

The database stores application data.

Examples:

- MySQL
- PostgreSQL
- Microsoft SQL Server
- Oracle Database
- MongoDB

---

# Three-Tier Architecture

Modern web applications commonly use a three-tier architecture.

```
Presentation Layer
        │
Application Layer
        │
Data Layer
```

### Presentation Layer

Handles user interaction.

Technologies:

- HTML
- CSS
- JavaScript

---

### Application Layer

Processes business logic.

Examples:

- Authentication
- Authorization
- Input validation
- API processing

---

### Data Layer

Stores application information.

Examples:

- User accounts
- Orders
- Products
- Customer records
- Financial transactions

---

# Client-Side Processing

Client-side processing occurs inside the user's browser.

Common technologies:

- HTML
- CSS
- JavaScript

Advantages:

- Faster response
- Better user experience
- Reduced server workload

---

# Server-Side Processing

Server-side processing occurs on the web server.

Responsibilities:

- Processing requests
- Business logic
- Authentication
- Database interaction
- Security validation

---

# HTTP Request–Response Cycle

```
Browser
   │
HTTP Request
   │
   ▼
Web Server
   │
Application Server
   │
Database
   │
Application Server
   │
HTTP Response
   │
Browser
```

---

# Dynamic Web Applications

Dynamic applications generate content based on:

- User identity
- Database records
- User preferences
- Business rules
- Current time

Examples:

- Email dashboards
- Shopping carts
- Online banking
- Social media feeds

---

# Common Frontend Technologies

- HTML
- CSS
- JavaScript
- React
- Angular
- Vue.js

---

# Common Backend Technologies

- PHP
- ASP.NET
- Java
- Python
- Node.js
- Ruby

---

# Common Databases

- MySQL
- PostgreSQL
- SQL Server
- Oracle
- MongoDB

---

# Why Web Applications Are High-Value Targets

Attackers target web applications because they often:

- Are accessible from the Internet
- Store sensitive information
- Process financial transactions
- Handle customer data
- Support critical business operations

---

# Security Goals

A secure web application should provide:

- Confidentiality
- Integrity
- Availability
- Authentication
- Authorization
- Accountability

---

# Best Practices

- Keep software updated
- Validate all user input
- Use HTTPS
- Enforce strong authentication
- Apply least privilege
- Secure session management
- Log important security events
- Perform regular security testing

---

# CEH Exam Tips

Remember:

- A web application is different from a web server.
- Most modern applications follow a three-tier architecture.
- Client-side code runs in the browser.
- Server-side code runs on the server.
- Databases store application data.
- HTTP is the primary communication protocol for web applications.

---

# Key Takeaways

- Web applications are interactive software systems accessed through web browsers.
- They typically consist of clients, web servers, application servers, and databases.
- Secure architecture, proper authentication, input validation, and continuous monitoring are essential for protecting web applications.
