# Churn And Retention Analysis

## Table of Content
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Key Performance Indicator](#key-performance-indicator)
- [Data Analysis Expression](#data-analysis-expression)
- [Results](#results)
- [Recommendation](#recommendation)


### Project Overview
The primary aim of this dashboard is to analyze customer churn rates and identify key risk factors contributing to customer attrition. This helps businesses improve retention strategies and enhance customer satisfaction.

### Data Sources
The Primary dataset used for this analysis is the "" file.

### Tools
- Excel - Data Inspection
- Power Query - Data Cleaning 
- Power BI - EDA and Report Creation

### Data Cleaning
1. Data Inspection :Data Inspection was carried to identify duplicate values, missing values, checking datatype  
2. Handling Missing Values : Missing values were identified and were filled. 
3. Data Classification: Some Data were classified into categorical format for easy analysis.

### Key Performance Indicator
1. Distribution by Demography
   - Gender
   - Tenure(Years)
2. Customer Acct. Info Metrics
3. Service Customer Signedup Metrics
4. Customer Risk Analysis Distribution

### Data Analysis Expression

``` DAX
% Churn Rate = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Churn]),ALLSELECTED('01 Churn-Dataset'[Churn])))

% Dependents = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"))

% DiviceProtection = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[DeviceProtection]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"))

% multilinesNo = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="No",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines]<>"No phone service"))

% multilinesYes = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines]<>"No phone service"))

% Online Security = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[OnlineSecurity]="Yes",'01 Churn-Dataset'[Churn]="yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"))

% OnlineBackup = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[OnlineBackup]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"))

% Partner = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Churn]="Yes"))

% Phone Service = DIVIDE(CALCULATE(COUNTA('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[PhoneService]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNTA('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"))

% Senior Citizen = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"))

% StreamingMovie = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[StreamingMovies]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"))

% StreamingTV = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[StreamingTV]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"))

% TechSupport = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[TechSupport]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"))

Count Churn = CALCULATE(COUNT('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn]="Yes")
```

### Results
- The churn rate is 26.54%, indicating that over a quarter of customers are leaving.
- Customers with less than 1 year of tenure have the highest churn count (999 customers).
- Churn rate decreases significantly as tenure increases.
- Month-to-month contract customers are the most likely to churn.
- One-year and two-year contracts retain customers better.
- 25% of customers are senior citizens, and they show a higher churn tendency, possibly due to cost sensitivity or service usage patterns.

### Recommendation
- Offer discounts or incentives for customers switching from monthly to annual contracts.
- Provide a loyalty reward program for long-term customers.
- Reduce cancellation fees for long-term contracts to encourage sign-ups.
- Conduct a service quality survey for fiber optic customers to identify dissatisfaction points.
- Offer price-matching guarantees or bundle discounts to make fiber plans more attractive.
- Improve technical support response times for fiber optic users.

