# Comprehensive Employee Demographics and Performance Dashboard

## Project Overview
This project provides an interactive Power BI dashboard to analyze employee demographics, performance metrics, promotion rates, turnover, and hiring patterns. It aims to help HR and management make data-driven decisions to improve diversity, talent retention, and employee satisfaction.

## Objective
The key objectives of this dashboard are:
- Analyze gender distribution, promotions, and hiring patterns.
- Monitor employee turnover and performance ratings.
- Aid in strategic workforce management.

## Data Description
The dataset includes the following columns:
- **Employee ID**: Unique employee identifier.
- **Gender**: Gender of the employee (Male/Female).
- **Hire Date**: Date of employee's hire.
- **Promotion Date**: Last promotion date.
- **Status**: Active or Leaver.
- **Performance Rating**: Employee’s performance score.
- **Department**: Department of the employee.

## Key Metrics and DAX Calculations

1. **Number of Men**:
    ```DAX
    NumberOfMen = CALCULATE(COUNTROWS('EmployeeTable'), 'EmployeeTable'[Gender] = "Male")
    ```

2. **Number of Women**:
    ```DAX
    NumberOfWomen = CALCULATE(COUNTROWS('EmployeeTable'), 'EmployeeTable'[Gender] = "Female")
    ```

3. **Number of Leavers**:
    ```DAX
    NumberOfLeavers = CALCULATE(COUNTROWS('EmployeeTable'), 'EmployeeTable'[Status] = "Leaver")
    ```

4. **% of Employees Promoted (FY21)**:
    ```DAX
    EmployeesPromotedFY21 = CALCULATE(COUNTROWS('EmployeeTable'), 'EmployeeTable'[PromotionDate] >= DATE(2021,1,1), 'EmployeeTable'[PromotionDate] <= DATE(2021,12,31))
    PercentagePromotedFY21 = DIVIDE(EmployeesPromotedFY21, TotalEmployees) * 100
    ```

5. **% of Women Promoted**:
    ```DAX
    WomenPromoted = CALCULATE(COUNTROWS('EmployeeTable'), 'EmployeeTable'[PromotionDate] >= DATE(2021,1,1), 'EmployeeTable'[Gender] = "Female")
    PercentageWomenPromoted = DIVIDE(WomenPromoted, TotalEmployees) * 100
    ```

## Business Decisions to be Taken
- **Improve Gender Diversity**: Analyze gender distribution and address discrepancies.
- **Reduce Turnover**: Identify key turnover trends and take retention measures.
- **Enhance Promotions**: Ensure equal promotion opportunities across genders.
- **Targeted Hiring**: Improve recruitment strategies to align with diversity goals.

## How to Use
1. **Load the Dataset**: Ensure data is properly loaded into Power BI with appropriate data types.
2. **Visualize the Metrics**: Use filters and slicers to drill down into key metrics.
3. **Extract Insights**: Leverage the insights to make strategic HR and management decisions.

## Tools Used
- **Power BI**: For data visualization and dashboard creation.
- **DAX**: Data Analysis Expressions for creating metrics.
- **Git**: Version control for managing project updates.

## Author
- **Kurma Dinesh**: Data Analyst and Power BI Developer.
