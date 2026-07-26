# Dataset Summary

+ The dataset contains records for 311 employees across 36 features, covering demographic details, employment status,   salary, performance metrics, recruitment sources, and workplace engagement.

| Category | Key Columns | Description |
| :--- | :--- | :--- |
| **Demographics** | `Employee_Name`, `Sex`, `MaritalDesc`, `RaceDesc`, `CitizenDesc`, `DOB`, `State`, `Zip` | Personal demographic information of each employee. |
| **Employment & Role** | `Position`, `Department`, `EmploymentStatus`, `ManagerName`, `DateofHire`, `DateofTermination`, `TermReason` | Role titles, team structure, hiring dates, and exit reasons (if applicable). |
| **Compensation & Output** | `Salary`, `SpecialProjectsCount` | Annual salary in USD and count of assigned special projects. |
| **Performance & Behavior** | `PerformanceScore`, `EngagementSurvey`, `EmpSatisfaction`, `Absences`, `DaysLateLast30`, `LastPerformanceReview_Date` | Employee evaluation metrics, survey ratings (1–5 scale), attendance, and punctuality. |
| **Recruitment Channel** | `RecruitmentSource`, `FromDiversityJobFairID` | Platform or channel through which the employee was hired. |

#### 2. High-Level Data Insights

+ A. `Employment & Attrition Status:`

  + Active Employees: 207 (~66.6%)

  + Voluntarily Terminated: 88 (~28.3%)

  + Terminated for Cause: 16 (~5.1%)

+ B. `Salary Distribution`

+ Mean Salary: $69,020.68

+ Median Salary: $62,810.00

+ Minimum Salary: $45,046.00

+ Maximum Salary: $250,000.00

+ C. `Departmental Breakdown`

+ Production: 209 employees (~67.2%)

+ IT/IS: 50 employees (~16.1%)

+ Sales: 31 employees (~10.0%)

+ Software Engineering: 11 employees (~3.5%)

+ Admin Offices: 9 employees (~2.9%)

+ Executive Office: 1 employee (~0.3%)

+ D. `Performance Ratings`

+ Fully Meets: 243 employees (~78.1%)

+ Exceeds: 37 employees (~11.9%)

+ Needs Improvement: 18 employees (~5.8%)

+ PIP (Performance Improvement Plan): 13 employees (~4.2%)

+ E. `Top Recruitment Sources`

+ Indeed: 87 hires

+ LinkedIn: 76 hires

+ Google Search: 49 hires

+ Employee Referral: 31 hires

+ Diversity Job Fair: 29 hires

+ F. `Engagement & Attendance Highlights`

+ Average Engagement Survey Score: 4.11 / 5.0

+ Average Employee Satisfaction Score: 3.89 / 5.0

+ Average Absences per Employee: 10.24 days

+ Days Late in Last 30 Days: Average 0.41 days (Max: 6 days)

+  3. `Data Cleanliness & Missing Values`

+ DateofTermination: 207 missing values (This is expected since 207 employees are currently Active).

+ ManagerID: 8 missing values (Can be imputed using ManagerName).

+ All other 34 columns have 0 missing values and clean data types.