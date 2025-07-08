# Power BI Project: Employee Attrition & Performance Analysis

## 📁 Folder Name:
Employee_Attrition_PowerBI_CaseStudy

## 📄 Power BI File:
3_5_more_insights_solution.pbix

## 📌 Overview
This Power BI dashboard provides detailed insights into employee attrition, department performance, and demographic factors influencing workforce trends. It was built using a structured data model with dynamic visuals and navigation.

## 📂 Dataset
- Source File: Databel - Data.csv
- Contains key fields such as employee ID, department, education, satisfaction score, ratings, and attrition status.
- Used to create one fact table and four dimension tables within Power BI.

## 🧩 Data Modeling
- Fact Table: `PerformanceFact`
- Dimension Tables: `Employee`, `Education`, `Satisfaction`, `Rating`
- Total Relationships Created: **10**
  - Includes 1:* relationships for satisfaction ID, education ID, and rating ID
  - One active relationship for rating (manager/self)

## 🧠 DAX Measures
- `TotalEmployees = COUNT(Emp[EmpID])`
- `ActiveEmployees = CALCULATE(COUNT(Emp[EmpID]), Emp[Attrition] = "No")`
- `InactiveEmployees = [TotalEmployees] - [ActiveEmployees]`
- `AttritionRate = DIVIDE([InactiveEmployees], [TotalEmployees], 0)`

## 📊 Report Pages
1. **Overview** – KPIs, year-wise hiring trends, department insights
2. **Demographics** – Age, gender, education visuals
3. **Performance Tracker** – Manager vs self-rating analysis
4. **Attrition** – Filters based on satisfaction, education, job roles

## 🎛 Interactive Features
- Used **page navigation buttons** via: `View → Buttons → Navigator`
- Custom formatting: fill color, border, text state
- Applied filters like `Attrition = Yes` for focused insights
- Used `DimDate[Year]` from the hierarchy to group hiring trends

## 🛠 Tools Used
- Power BI Desktop
- CSV Dataset (Excel format)
- DAX formulas for KPIs and calculations

## ✅ Final Outcome
This project delivers a professional-grade dashboard that enables HR teams to explore workforce trends, track attrition rates, and understand which departments and roles may require intervention.
