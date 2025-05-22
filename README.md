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
👤 Student: Shema Yvan  
🆔 Student ID: [Insert Your Student ID]  
📚 Project Title: Work Seeker Platform – Job Matching & Training System

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





