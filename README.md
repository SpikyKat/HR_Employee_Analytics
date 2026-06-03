# HR Employee Analytics Project

This project contains a comprehensive HR employee data analysis with data cleaning, SQL analytics, and cleaned datasets.

## Project Structure

```
HR_Employee_Analytics/
├── data/
│   ├── HR_Employee_Cleaned_Data.csv          # Cleaned HR employee dataset
│   ├── HRDataset_v14.csv                     # Original HR dataset
├── notebooks/
│   ├── HR_Data_Cleaning.ipynb                # Data cleaning and transformation notebook
├── sql/
│   ├── HR_Analytics.sql                      # SQL queries for HR analytics
├── README.md                                  # Project documentation
└── .gitignore                                 # Git ignore file
```

## Overview

This HR Analytics project processes and analyzes employee data including:
- Employee demographics (name, age, marital status, race, citizenship)
- Employment information (department, position, hire date, termination date, status)
- Performance metrics (performance score, engagement survey, satisfaction, absences)
- Compensation data (salary)
- Management information (manager assignments)

## Files Included

### 1. Data Files

#### HR_Employee_Cleaned_Data.csv
- Cleaned and processed employee dataset
- 311 employee records
- Fixed formatting issues and data types
- Filled missing ManagerID values
- Converted date columns to proper datetime format
- Reformatted employee names from "Last, First" to "First Last"

#### HRDataset_v14.csv
- Original HR dataset
- Contains raw data with various encoding and formatting issues
- Used as source for data cleaning process

### 2. Jupyter Notebook

#### HR_Data_Cleaning.ipynb
Comprehensive data cleaning notebook including:
- Data import and exploration
- Missing value analysis
- Data type conversions
- Employee name reformatting
- Removal of redundant columns
- Data validation and quality checks

**Key cleaning steps:**
- Fixed 8 missing ManagerID values (assigned to manager Webster Butler with ID 39)
- Converted date columns (DOB, DateofHire, DateofTermination, LastPerformanceReview_Date) to datetime format
- Reformatted employee names from "Last, First" format to "First Last" format
- Dropped redundant ID columns: MarriedID, MaritalStatusID, GenderID, Termd, PerfScoreID, EmpStatusID, PositionID
- Reordered columns for better organization and readability

### 3. SQL Analytics

#### HR_Analytics.sql
SQL database setup and analytical queries:

**Database Setup:**
- Creates HR_Employee_DB database
- Creates HR_Employee table with appropriate data types and constraints

**Sample Queries Included:**
- Average salary by department
- Count of diversity recruitment hires
- Employee breakdown by race/ethnicity
- Gender distribution analysis
- Performance score distribution
- Employees with low performance ratings
- Top performers by department
- Termination analysis
- And more...

## Data Dictionary

| Column | Description |
|--------|-------------|
| EmpID | Employee ID (Primary Key) |
| Employee_Name | Employee full name |
| Sex | Gender (M/F) |
| MaritalDesc | Marital status |
| DeptID | Department ID |
| FromDiversityJobFairID | Diversity job fair recruitment flag (0/1) |
| Salary | Annual salary |
| Position | Job position |
| State | State of residence |
| Zip | Zip code |
| DOB | Date of birth |
| CitizenDesc | Citizenship status |
| HispanicLatino | Hispanic/Latino flag (Yes/No) |
| RaceDesc | Race/Ethnicity description |
| DateofHire | Hire date |
| DateofTermination | Termination date (NULL if still employed) |
| TermReason | Reason for termination |
| EmploymentStatus | Current employment status (Active/Terminated) |
| Department | Department name |
| ManagerName | Manager's name |
| ManagerID | Manager's ID |
| RecruitmentSource | Source of recruitment |
| PerformanceScore | Performance rating |
| EngagementSurvey | Employee engagement score |
| EmpSatisfaction | Employee satisfaction rating |
| SpecialProjectsCount | Number of special projects |
| LastPerformanceReview_Date | Last performance review date |
| DaysLateLast30 | Days late in last 30 days |
| Absences | Total absences |

## Data Quality Issues Resolved

1. **Missing ManagerID Values:** 8 records with manager "Webster Butler" had missing ManagerID
   - Solution: Filled with ManagerID 39 (Webster Butler's ID)

2. **Date Format Inconsistencies:** All date columns were stored as strings
   - Solution: Converted to datetime64[ns] format

3. **Employee Name Format:** Names were in "Last, First" format
   - Solution: Reformatted to "First Last" format

4. **Redundant Columns:** Contained both coded IDs and descriptions
   - Solution: Dropped: MarriedID, MaritalStatusID, GenderID, Termd, PerfScoreID, EmpStatusID, PositionID

## Key Statistics

- **Total Employees:** 311
- **Active Employees:** 207
- **Terminated Employees:** 104
- **Departments:** 6 (Production, IT/IS, Sales, Admin Offices, Software Engineering, Executive Office)
- **Average Salary:** $69,000+ (varies by department)

## How to Use

1. **For Data Analysis:** Use the cleaned CSV file (`data/HR_Employee_Cleaned_Data.csv`)
2. **For Database Setup:** Run the SQL scripts in `sql/HR_Analytics.sql`
3. **For Understanding the Process:** Review the Jupyter notebook `notebooks/HR_Data_Cleaning.ipynb`

## Technologies Used

- **Python:** Data cleaning and transformation
- **Pandas:** Data manipulation and analysis
- **SQL:** Database queries and analytics
- **MySQL:** Database management system
- **Jupyter Notebook:** Interactive analysis environment

## Future Enhancements

- Advanced statistical analysis
- Predictive modeling for employee turnover
- Interactive dashboards (Tableau/Power BI)
- Department-specific analytics
- Compensation benchmarking
- Performance trend analysis

## Author

Created as part of HR Analytics project

## License

MIT License - Feel free to use this project for your own analysis
