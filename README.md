# SQL Filters Unleashed for Security Enhancement

## Background

In the relentless pursuit of fortifying our organization's digital bastion, my role as a security professional involves investigating potential security issues to ensure the sanctity of our system. Focusing on login attempts and employee machines, this project unveils the strategic use of SQL filters to delve into our organization's data and unveil security nuances.

## Objectives

The overarching objectives of this project are as follows:

1. **After-Hours Login Investigation:**
   - Scrutinize failed login attempts after business hours (post 18:00), identifying potential security incidents.

2. **Date-Specific Login Analysis:**
   - Investigate login attempts on specific dates, responding to suspicious events and ensuring comprehensive security.

3. **Geographical Anomaly Detection:**
   - Uncover and investigate login attempts originating outside of Mexico, addressing potential anomalies in the login data.

4. **Departmental Computer Updates:**
   - Streamline the process of updating computers for employees in specific departments, ensuring targeted security enhancements.

5. **Departmental Exclusion Security Check:**
   - Identify and update computers for employees in Finance and Sales departments, tailoring security measures to the unique needs of these departments.

6. **Non-IT Employee Security Update:**
   - Implement security updates for employees not affiliated with the Information Technology department, ensuring a comprehensive security posture.

## Supporting Material

Delve into the intricacies of our organization's data structures with the [Table Formats document](https://github.com/JustinAntunes-Cardoso/SQL-Security-Filters/blob/main/Table-formats.docx), providing a roadmap for understanding the tables utilized in this project.

## Project Steps

### 1. Retrieve After-Hours Failed Login Attempts
```sql
SELECT * FROM log_in_attempts WHERE login_time > '18:00' AND success = FALSE;
```

### 2. Retrieve Login Attempts on Specific Dates
```sql
SELECT * FROM log_in_attempts WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```

### 3. Retrieve Login Attempts Outside of Mexico
```sql
SELECT * FROM log_in_attempts WHERE NOT country LIKE 'MEX%';
```

### 4. Retrieve Employees in Marketing in the East Building
```sql
SELECT * FROM employees WHERE department = 'Marketing' AND office LIKE 'East%';
```

### 5. Retrieve Employees in Finance or Sales
```sql
SELECT * FROM employees WHERE department = 'Finance' OR department = 'Sales';
```

### 6. Retrieve All Employees Not in IT
```sql
SELECT * FROM employees WHERE NOT department = 'Information Technology';
```

## Project Conclusion
In this SQL-filtered journey, specific data subsets have been meticulously examined, laying the foundation for targeted security enhancements. By deploying the AND, OR, and NOT operators, along with LIKE patterns, this project ensures that our security measures align with the nuanced needs of different facets within our organization.

## Feedback
Your insights are invaluable. Review the detailed project steps and outcomes in the provided [GitHub repository](https://github.com/JustinAntunes-Cardoso/SQL-Security-Filters) and share your thoughts.

---

**Note:** I've independently completed this project.
