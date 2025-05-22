# wedn_26723_yvan_workseeker_FINAL-EXAM
# PL/SQL EXAM  
## 👤 Student:ZIKAMABAHARI Shema Yvan  
## 🆔 ID: 26723  
## 🧬 Project Title: WORK SEEKER PLATFORM – FIND YOUR DREAM JOB  

---

## 🌀 Phase I – Introduction

In Rwanda and many developing countries, young graduates and job seekers face significant barriers to employment due to a mismatch between their skills and job market needs. Additionally, employers struggle to find properly trained candidates who meet the evolving standards of the labor market. 

The Work Seeker Platform is a PL/SQL-driven database system designed to support unemployed individuals by facilitating structured access to career guidance, training programs, and employer job listings. This system aims to automate the job search and training enrollment process, improving the efficiency of job matching between job seekers and organizations in need of qualified personnel.

By centralizing job seeker data, training records, and employer job posts, the platform reduces the burden of manual tracking and enhances data security, access, and decision-making.

---

## 🎯 Problem Statement

Many Rwandan youth face unemployment due to lack of job-ready skills, inefficient job-matching systems, and limited exposure to real job opportunities. Traditional employment centers lack automation and cannot effectively match candidates based on qualifications and career interests.

At the same time, companies and organizations spend unnecessary time and resources reviewing unqualified candidates because there's no structured database connecting them to the right talent pool. The absence of such a platform creates inefficiencies on both the supply and demand side of the labor market.

---

## 👁️ Context

The Work Seeker Platform is designed for deployment in:
- 🏢 Employment agencies
- 🎓 Training institutions
- 🏭 Private sector companies
- 🏛️ Government job support initiatives
- 🤝 NGO-driven employment and empowerment programs

It will serve as a centralized solution for registering job seekers, assigning them to relevant training, and matching them with job vacancies posted by employers based on their qualifications.

---

## 🧑‍💼 Target Users

- 🎯 Job Seekers – Individuals actively seeking training or employment.
- 🎓 Training Providers – Institutions or NGOs offering short/long-term upskilling programs.
- 🏢 Employers – Businesses or organizations with active job vacancies.
- 🏛️ Government and NGOs – Partners interested in improving national employment outcomes.

---

## 🎯 Project Goals

- **Automate** registration, training, and job application workflows.
- **Improve accuracy** of candidate-job matching using skill-based filters and structured SQL queries.
- **Enhance security** for storing sensitive user and company information.
- **Increase employment** by streamlining the path from training to hiring.
- **Support scalability** for future integration with government portals and job boards.

---

## 🧱 Database Design (Main Entities)

- **Job_Seeker** (`Seeker_ID`, Name, Contact, Education, Job_Level, Skills)
- **Training_Program** (`Program_ID`, Name, Description, Duration)
- **Enrollment** (`Enrollment_ID`, Seeker_ID, Program_ID, Completion_Status)
- **Employer** (`Employer_ID`, Company_Name, Industry, Contact)
- **Job_Vacancy** (`Job_ID`, Employer_ID, Job_Title, Skills_Required, Status)
- **Job_Application** (`Application_ID`, Seeker_ID, Job_ID, Status)

---

> This system is envisioned to transform the way job seekers and employers interact in Rwanda, serving as a digital bridge between education, skills, and employment.
# 🌀 Phase II – Business Process Modeling  
📚 Project Title: Work Seeker Platform – Job Matching & Training System

---

## 🗺️ 1. Define the Scope

### 🔄 Business Process:  
Job Matching and Training Enrollment for Job Seekers

### 📜 Description:  
This process models how unemployed individuals register on the platform, complete their profile, enroll in training programs if necessary, and apply for jobs that match their skills. The system suggests relevant opportunities based on their qualifications and automates the job matching workflow.

The platform integrates seamlessly with a Management Information System (MIS) by tracking all interactions, training progress, and job application statuses, providing structured data for decision-making and reporting.

---

### 🎯 Objectives:
- Streamline the job search and application process.
- Ensure job seekers gain relevant skills through training programs.
- Automatically match candidates to vacancies using SQL queries based on qualifications and skills.
- Help employers find qualified candidates more efficiently.

---

### 📈 Expected Outcomes:
- Faster and more accurate job matching.
- Increased training participation by job seekers.
- Reduced unemployment through smarter recommendations.
- Real-time tracking of applications and training progress for decision support.

---

## 🧩 2. Identify Key Entities

| Entity / Actor     | Role & Responsibilities                                                                 |
|--------------------|------------------------------------------------------------------------------------------|
| **Job Seeker**     | Registers, completes profile, enrolls in training, applies for jobs.                     |
| **Training Provider** | Offers skill-building programs and tracks completions.                                |
| **Employer**       | Posts job vacancies and hires candidates matched by the system.                          |
| **System Database**| Stores user profiles, training records, job posts, and applications.                    |
| **Government/NGOs**| May support or fund training and employment initiatives.                                 |

---

## 🏊 Swimlanes to Use

The BPMN diagram is organized into the following lanes:

- **Job Seeker** – Registration, training, and job application.
- **Training Provider** – Manages program validation and completion.
- **Employer** – Posts jobs and reviews applications.
- **System** – Matches skills to vacancies and automates workflows.

---

## 🖇️ UML / BPMN Presentation

The visual diagram uses:
- **Ovals** for start/end points
- **Rectangles** for tasks
- **Diamonds** for decision nodes
- **Arrows** to show flow
-
![1b75e188-0a25-44e3-876e-eee6ea4ffdc9](https://github.com/user-attachments/assets/4f779ad5-fd2a-4876-849c-9011fdf25d95)


---

## 💬 Explanation of the BPMN Diagram

### ✍️ Main Components and Interactions:
The process begins with a **job seeker** registering and completing their profile. If their skills are insufficient, the system recommends training programs. The seeker enrolls, and the training provider tracks progress.

Once completed, the system uses stored SQL logic to match the seeker with relevant job opportunities. The seeker applies, and the **employer** reviews applications. All interactions are stored in the **system database**, which can be analyzed by MIS tools for performance tracking and decision-making.

---

### 🧠 How This Supports MIS Functions:
- **Improved Decision-Making**: Data on enrollments, applications, and hires feed MIS dashboards.
- **Workflow Automation**: From registration to hiring, everything is logged and traceable.
- **Reporting & Analytics**: Supports tracking key KPIs (e.g., training completion rate, application success rate).

---

### 📌 Importance for Organizational Efficiency

This process improves efficiency by removing manual bottlenecks in employment systems. Employers find candidates faster, job seekers are better prepared through training, and MIS administrators can track all activity. The platform bridges the education-to-employment gap and contributes to national workforce development efforts.


# ✅ Phase III – Logical Model Design  
---

## 🔢 1. Entity-Relationship (ER) Model

| Entity             | Attributes                                                           | Keys                          | Data Types                          |
|--------------------|----------------------------------------------------------------------|-------------------------------|--------------------------------------|
| **Job_Seeker**     | seeker_id, name, contact, education, job_level, skills               | PK: seeker_id                 | NUMBER, VARCHAR, VARCHAR             |
| **Training_Program**| program_id, name, description, duration                             | PK: program_id                | NUMBER, VARCHAR                      |
| **Enrollment**     | enrollment_id, seeker_id, program_id, completion_status              | PK: enrollment_id<br>FKs: seeker_id, program_id | NUMBER, VARCHAR, VARCHAR |
| **Employer**       | employer_id, company_name, industry, contact                         | PK: employer_id               | NUMBER, VARCHAR                      |
| **Job_Vacancy**    | job_id, employer_id, job_title, skills_required, status              | PK: job_id<br>FK: employer_id | NUMBER, VARCHAR                      |
| **Job_Application**| application_id, seeker_id, job_id, status                            | PK: application_id<br>FKs: seeker_id, job_id | NUMBER, VARCHAR           |

---

## 🔃 2. Relationships & Constraints

### Relationships

| From Entity     | To Entity        | Type      | Description                                           |
|------------------|------------------|-----------|-------------------------------------------------------|
| Job_Seeker       | Enrollment       | One-to-Many | One seeker can enroll in multiple training programs   |
| Training_Program | Enrollment       | One-to-Many | One program can have many seekers                     |
| Employer         | Job_Vacancy      | One-to-Many | One employer can post multiple job vacancies          |
| Job_Seeker       | Job_Application  | One-to-Many | One seeker can apply for many jobs                    |
| Job_Vacancy      | Job_Application  | One-to-Many | One job can receive many applications                 |

### Constraints

- All IDs are `NOT NULL` and `PRIMARY KEY`
- Foreign Keys enforce relationships
- `Status` fields:
  - `Job_Application.status`: CHECK ('Pending', 'Accepted', 'Rejected')
  - `Job_Vacancy.status`: CHECK ('Open', 'Closed')
- `Completion_Status` in `Enrollment`: CHECK ('Completed', 'Ongoing', 'Not Started')

---

## 📦 3. Normalization (Up to 3NF)

| Form | Explanation |
|------|-------------|
| **1NF** | No repeating groups, all attributes are atomic |
| **2NF** | No partial dependencies (non-key attributes depend on full PK) |
| **3NF** | No transitive dependencies between non-key attributes |

---

## 🌍 4. Handling Real-World Data Scenarios

- Tracks training progress and completion through `Enrollment`.
- Matches seekers to jobs via skill matching logic in `Job_Vacancy` and `Job_Seeker`.
- Logs all job applications and their statuses for employers and administrators.
- Scalable structure to add login, location tracking, or performance metrics in future versions.

---

## 📊 5. ER Diagram Presentation

The logical model is supported by a visual **Entity-Relationship Diagram (ERD)** showing:

- Tables (entities)
- Relationships (1:M, M:N)
- Primary and foreign keys

![111111](https://github.com/user-attachments/assets/3d3aa207-9978-4421-a884-85e86ee19473)

# 🌀 Phase IV  
## Pluggable Database Creation – PDB Setup    
---

## 📠 What This Phase Covers  

This phase focuses on creating a **Pluggable Database (PDB)** and converting the logical model into a physical database structure. It ensures that all tables, relationships, and constraints are implemented to meet the requirements of the Work Seeker system.

---

## 🔨 Database Creation  

The pluggable database was created following the standard naming convention:

- **Database Name:** `wedn_26723_shema_workseeker_db`  
- **Username:** `yvan`  
- **Password:** `yvan`  

---

## ✅ Steps Executed in SQL Command Prompt  

1.Created a pluggable database

![image](https://github.com/user-attachments/assets/08554f3e-7e49-4904-89d9-e4573dd1f989)

2. Opened the newly created PDB  

![image](https://github.com/user-attachments/assets/5b8b7a4e-457e-4bce-9c2f-edf5e03de9a4)

3. Saved the PDB to retain its open state
   
 ![image](https://github.com/user-attachments/assets/bd68f40c-4a4e-4d86-8655-1ae30422516f)
  
4. Set the session container to the new PDB
   
   ![image](https://github.com/user-attachments/assets/f0b55c02-be7b-4d2e-b4b0-fede4dfaa476)

5. Created a user and granted all necessary privileges  

![image](https://github.com/user-attachments/assets/36ef39a6-0e45-44fe-868c-75d635bd419f)

---

## ⚖️ Oracle Enterprise Manager (OEM)  

Oracle Enterprise Manager (OEM) was used to verify:
- ✅ The PDB was successfully created and opened  
- ✅ The user `yvan` was created and granted full privileges  
- ✅ Sessions and activity could be monitored  
- ✅ Schema-level structure and table space were active
  
![image](https://github.com/user-attachments/assets/22a2be02-0d5b-4c64-9f60-0610896ed47f)

---

## 🔭 Conclusion About This Phase  

This phase successfully established the **pluggable database** for the Work Seeker system and validated its functionality via SQL and OEM tools.

The system is now ready to support:
- Table creation  
- Transactional logic  
- Procedure and function development  
- Full PL/SQL implementation in upcoming phases  


# 🌀 Phase V  
## Physical Database Structure  
---

## 🧱 Table Creation  

This phase converts the logical Entity-Relationship model into a **physical Oracle database structure**, implementing all required tables, relationships, and data integrity constraints for the Work Seeker Platform. The system supports job seeker registration, training program enrollment, job applications, and employer vacancy listings.

---

### 📋 Job Seeker Table
```sql
CREATE TABLE "YVAN"."JOB_SEEKER" 
   (	"SEEKER_ID" NUMBER, 
	"NAME" VARCHAR2(100 BYTE) NOT NULL ENABLE, 
	"CONTACT" VARCHAR2(50 BYTE), 
	"EDUCATION" VARCHAR2(100 BYTE), 
	"JOB_LEVEL" VARCHAR2(50 BYTE), 
	"SKILLS" VARCHAR2(255 BYTE), 
	 PRIMARY KEY ("SEEKER_ID")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 COMPUTE STATISTICS 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 
 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
```
---

### 📋 Training Program Table  
```sql
CREATE TABLE "YVAN"."TRAINING_PROGRAM" 
   (	"PROGRAM_ID" NUMBER, 
	"NAME" VARCHAR2(100 BYTE) NOT NULL ENABLE, 
	"DESCRIPTION" VARCHAR2(255 BYTE), 
	"DURATION" VARCHAR2(50 BYTE), 
	 PRIMARY KEY ("PROGRAM_ID")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 COMPUTE STATISTICS 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 
 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
```
---

### 📋 Enrollment Table  
```sql
CREATE TABLE Enrollment (
    Enrollment_ID     NUMBER PRIMARY KEY,
    Seeker_ID         NUMBER,
    Program_ID        NUMBER,
    Completion_Status VARCHAR2(20) CHECK (Completion_Status IN ('Completed', 'Ongoing', 'Not Started')),
    FOREIGN KEY (Seeker_ID) REFERENCES Job_Seeker(Seeker_ID),
    FOREIGN KEY (Program_ID) REFERENCES Training_Program(Program_ID)
);
```
---

### 📋 Employer Table  
```sql
CREATE TABLE "YVAN"."EMPLOYER" 
   (	"EMPLOYER_ID" NUMBER, 
	"COMPANY_NAME" VARCHAR2(100 BYTE) NOT NULL ENABLE, 
	"INDUSTRY" VARCHAR2(100 BYTE), 
	"CONTACT" VARCHAR2(50 BYTE), 
	 PRIMARY KEY ("EMPLOYER_ID")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 COMPUTE STATISTICS 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 
 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
  ```

---

### 📋 Job Vacancy Table  
```sql
CREATE TABLE "YVAN"."JOB_VACANCY" 
   (	"JOB_ID" NUMBER, 
	"EMPLOYER_ID" NUMBER, 
	"JOB_TITLE" VARCHAR2(100 BYTE), 
	"SKILLS_REQUIRED" VARCHAR2(255 BYTE), 
	"STATUS" VARCHAR2(20 BYTE), 
	 CHECK (Status IN ('Open', 'Closed')) ENABLE, 
	 PRIMARY KEY ("JOB_ID")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 COMPUTE STATISTICS 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE, 
	 FOREIGN KEY ("EMPLOYER_ID")
	  REFERENCES "YVAN"."EMPLOYER" ("EMPLOYER_ID") ENABLE
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 
 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
```
---

### 📋 Job Application Table  
```sql
CREATE TABLE "YVAN"."JOB_APPLICATION" 
   (	"APPLICATION_ID" NUMBER, 
	"SEEKER_ID" NUMBER, 
	"JOB_ID" NUMBER, 
	"STATUS" VARCHAR2(20 BYTE), 
	 CHECK (Status IN ('Pending', 'Accepted', 'Rejected')) ENABLE, 
	 PRIMARY KEY ("APPLICATION_ID")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 COMPUTE STATISTICS 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE, 
	 FOREIGN KEY ("SEEKER_ID")
	  REFERENCES "YVAN"."JOB_SEEKER" ("SEEKER_ID") ENABLE, 
	 FOREIGN KEY ("JOB_ID")
	  REFERENCES "YVAN"."JOB_VACANCY" ("JOB_ID") ENABLE
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 
 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1
  BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
```

---

## ✍️ Data Insertion  

The following section includes sample records to simulate a real-world job matching environment.

---

### 📋 Job Seeker Table – Sample Data  
```
-- JOB SEEKERS
INSERT INTO Job_Seeker VALUES (1, 'Alice Niyonsaba', '0781111111', 'Bachelor in IT', 'Junior', 'SQL, Python');
INSERT INTO Job_Seeker VALUES (2, 'Eric Uwimana', '0782222222', 'Diploma in Business', 'Entry', 'Sales, Communication'); 
```
---

### 📋 Training Program Table – Sample Data  
```
-- TRAINING PROGRAMS
INSERT INTO Training_Program VALUES (101, 'SQL Basics', 'Intro to SQL', '4 weeks');
INSERT INTO Training_Program VALUES (102, 'Job Prep', 'Resume & Interview Coaching', '2 weeks');
``` 

---

### 📋 Enrollment Table – Sample Data  
```
-- ENROLLMENT
INSERT INTO Enrollment VALUES (1001, 1, 101, 'Completed');
INSERT INTO Enrollment VALUES (1002, 2, 102, 'Ongoing');
```
---

### 📋 Employer Table – Sample Data  
```
-- EMPLOYERS
INSERT INTO Employer VALUES (201, 'TechBridge Ltd.', 'IT Services', 'info@techbridge.com');
INSERT INTO Employer VALUES (202, 'SmartSales Inc.', 'Retail', 'contact@smartsales.com');
```
---

### 📋 Job Vacancy Table – Sample Data  
```
-- JOB VACANCIES
INSERT INTO Job_Vacancy VALUES (301, 201, 'Junior Developer', 'SQL, Python', 'Open');
INSERT INTO Job_Vacancy VALUES (302, 202, 'Sales Associate', 'Sales, Communication', 'Open');
```

---
### 📋 Job Application Table – Sample Data  
```
-- JOB APPLICATIONS
INSERT INTO Job_Application VALUES (401, 1, 301, 'Pending');
INSERT INTO Job_Application VALUES (402, 2, 302, 'Pending');
```

---

## 🧾 Summary  

This phase established the physical database structure for the **Work Seeker Platform**. All primary entities from the ER model were created as tables with appropriate constraints and relationships, including:

- Primary keys  
- Foreign key references  
- Data validation (via `NOT NULL`, `CHECK`, etc.)

Sample data was inserted to enable testing and to simulate user interactions within the system.

The database is now ready for PL/SQL programming in upcoming phases.







