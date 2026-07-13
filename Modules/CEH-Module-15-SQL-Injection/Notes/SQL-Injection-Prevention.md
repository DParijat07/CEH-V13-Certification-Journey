# SQL Injection Prevention

## Overview

SQL Injection prevention is a fundamental aspect of secure web application development. Organizations should adopt a **defense-in-depth** strategy by combining secure coding practices, proper database configuration, strong authentication, and continuous monitoring.

Preventing SQL Injection is significantly more effective than detecting and responding to attacks after deployment.

---

# Secure Software Development Life Cycle (SSDLC)

Security should be integrated into every phase of software development.

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
- Patch management
- Continuous monitoring

---

# Input Validation

All user input should be considered **untrusted** until validated.

Common input sources:

- Login forms
- Registration forms
- Search boxes
- Contact forms
- URL parameters
- Cookies
- HTTP headers
- API requests
- File uploads

### Best Practices

- Validate all input
- Use allowlists where possible
- Restrict input length
- Verify data types
- Reject unexpected characters
- Perform server-side validation

---

# Parameterized Queries

Parameterized queries separate SQL statements from user-supplied data.

### Benefits

- Prevent SQL Injection
- Improve code maintainability
- Supported by modern programming languages
- Recommended by OWASP

Parameterized queries are considered the **primary defense** against SQL Injection.

---

# Prepared Statements

Prepared statements define SQL queries before user input is supplied.

### Advantages

- Separate code from data
- Reduce SQL Injection risk
- Improve performance for repeated queries
- Widely supported across database platforms

---

# Stored Procedures

Stored procedures are SQL routines stored within the database.

### Advantages

- Centralized business logic
- Improved maintainability
- Consistent query execution

> **Note:** Stored procedures improve security only when implemented securely. They are **not** a replacement for parameterized queries or secure coding practices.

---

# Principle of Least Privilege (PoLP)

Applications should connect to databases using accounts with **only the minimum permissions required**.

Avoid:

- Administrative database accounts
- Shared privileged accounts
- Excessive permissions

Benefits:

- Limits attacker capabilities
- Reduces the impact of compromise
- Improves accountability

---

# Secure Error Handling

Applications should never expose detailed database errors to end users.

### Best Practices

- Display generic error messages
- Log detailed errors internally
- Protect log integrity
- Review logs regularly

---

# Database Hardening

Secure database configuration reduces the overall attack surface.

Recommendations:

- Remove unused accounts
- Disable unnecessary services
- Change default credentials
- Restrict remote access
- Enable encryption
- Configure secure authentication
- Review user permissions regularly

---

# Patch Management

Keep all database components updated.

Update:

- Database server
- Operating system
- Database drivers
- Client libraries
- Application frameworks

Regular patching reduces exposure to known vulnerabilities.

---

# Logging and Monitoring

Maintain detailed logs for security-related events.

Examples:

- Login attempts
- Failed authentication
- Administrative actions
- Permission changes
- Query failures
- Configuration changes

### Recommendations

- Centralize logs
- Protect log integrity
- Synchronize system time
- Configure alerts
- Review logs regularly

---

# Database Activity Monitoring (DAM)

Database Activity Monitoring solutions provide visibility into database operations.

### Benefits

- Detect unusual activity
- Identify unauthorized access
- Support compliance
- Improve incident response

---

# Web Application Firewall (WAF)

A Web Application Firewall filters HTTP and HTTPS traffic before it reaches the application.

### Benefits

- Blocks known attack patterns
- Filters malicious requests
- Reduces exposure to common web attacks
- Provides additional visibility

Examples:

- ModSecurity
- Cloudflare WAF
- AWS WAF
- Azure Web Application Firewall

---

# Secure Coding Checklist

Developers should:

- Validate all user input
- Use parameterized queries
- Implement prepared statements
- Avoid unnecessary dynamic SQL
- Apply the Principle of Least Privilege
- Handle errors securely
- Keep dependencies updated
- Perform regular code reviews
- Conduct security testing before deployment

---

# Security Testing

Organizations should regularly perform:

- Secure Code Reviews
- Static Application Security Testing (SAST)
- Dynamic Application Security Testing (DAST)
- Interactive Application Security Testing (IAST)
- Software Composition Analysis (SCA)
- Vulnerability Assessments
- Authorized Penetration Testing

---

# Defense-in-Depth

No single control can eliminate SQL Injection risk.

An effective strategy combines:

- Secure coding
- Input validation
- Parameterized queries
- Prepared statements
- Least privilege
- Database hardening
- Patch management
- Logging and monitoring
- Web Application Firewall
- Continuous security testing

---

# CEH Exam Tips

Remember:

- Parameterized queries are the preferred defense against SQL Injection.
- Prepared statements separate code from user input.
- Input validation alone is not sufficient.
- Least Privilege reduces the impact of compromise.
- Secure error handling prevents information disclosure.
- Defense-in-depth provides multiple layers of protection.

---

# Key Takeaways

- SQL Injection prevention starts with secure application design.
- Secure coding, parameterized queries, and prepared statements are the most effective technical controls.
- Database hardening, least privilege, logging, monitoring, and regular security testing provide additional layers of defense.
- Security should be integrated throughout the Secure Software Development Life Cycle (SSDLC) rather than added after deployment.
