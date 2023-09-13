# Bank-Term-Deposit-Subscription-Analysis
## Introduction
This documentation provides an overview of two Power BI dashboard created to analyze a bank term deposit subscription dataset. The dashboard contains measures and charts that answer specific questions related to the dataset.
## Data Source
The data source used for this analysis is the bank term deposit subscription dataset, which includes various columns such as age, marital status, education, default status, loan status, duration, and more.

## Dashboard Contents 1
![](https://github.com/AnietieJohnson/Bank-Term-Deposit-Subscription-Analysis/blob/main/Task%203.png)
## Measures
### 1. Average Age of Depositors
This measure calculates the average age of customers who have subscribed to a term deposit, Using the aggregate function **Average**
> Average age of Depositors = AVERAGE('bank-full'[Age]) 
### 2. Total Count of Term Deposit Subscribers
This measure counts the number of customers who have subscribed to a term deposit, Using the aggregate function **Count**
> Count of Depositors on Loan = CALCULATE(COUNT('bank-full'[Loan]), FILTER('bank-full','bank-full'[Loan] = "Yes"))
### 3. Count of Depositors on Loan
This measure counts the number of customers who have loans, Using the aggregate function **Count**
> Count of Subscribers = CALCULATE(COUNT('bank-full'[Y]), FILTER('bank-full','bank-full'[Y] ="Yes"))
### 4. Average Duration Of Customer Interaction
This measure calculates the average duration of interactions with customers during the marketing campaign,  Using the aggregate function **Average**
> Average Duration = AVERAGE('bank-full'[Duration])
### 5. Guage For Number of Subscribers
This visuals keeps check of increase in subscribers. A target is set to guide the measurement.
## Column Charts
### 1. Count of Subscribers by Marital Status
This column chart visualizes the count of subscribers categorized by their marital status. It helps in understanding how subscription rates vary among different marital statuses.
### 2. Count of Subscribers by Education
This column chart visualizes the count of subscribers categorized by their education level. It provides insights into the education background of subscribers.
### 3. Count of Subscribers by Default and Loan
This column chart displays the count of subscribers based on their default status and loan status. It helps in identifying whether subscribers tend to have previous defaults or loans.

## Dashboard Content 2
![](https://github.com/AnietieJohnson/Bank-Term-Deposit-Subscription-Analysis/blob/main/Task%204.png)
## Measures and Conditional Column Creation
### 1. Measure: Average Age of Depositors
This measure calculates the average age of customers who have subscribed to a term deposit,  Using the aggregate function **Average**
> Average age of Depositors = AVERAGE('bank-full'[Age])
### 2. Conditional Column: Age Band
Using power query a conditional column named "Age Band" is created based on the age of depositors, categorizing them as follows:
'Young' for ages below 30
'Mid-aged' for ages between 30 and 50
'Old' for ages above 50
![](https://github.com/AnietieJohnson/Bank-Term-Deposit-Subscription-Analysis/blob/main/New%20Column.png)
### 3. Measure: Total Balance for Job (Technician) and Marital (Single and Married)
This measure calculates the total balance for depositors with the following characteristics, using the **Calculate function_**
- Job: Technician, 
>Total Balance for Technicians = CALCULATE(SUM('bank-full'[Balance]),FILTER('bank-full','bank-full'[Job] = "Technician")) 
- Marital Status: Single and then for married.
>Total Balance for Single = CALCULATE(SUM('bank-full'[Balance]), FILTER('bank-full','bank-full'[Marital] ="Single"))
### 4. Measure: Number of Depositors on Loan
This measure counts the number of depositors who have loans,Using the aggregate function **Count** 
> Count of Depositors on Loan = CALCULATE(COUNT('bank-full'[Loan]), FILTER('bank-full','bank-full'[Loan] = "Yes"))

## Conclusion
This Power BI dashboard offers valuable insights into the bank term deposit subscription dataset, enabling us to analyze the average age of depositors, subscription counts, loan counts, average duration, and subscriber demographics. The second dashboard allows us to calculate total balances for specific job and marital status combinations, and determine the number of depositors with loans. These tools enhances ability to understand customer demographics and financial profiles, ultimately supporting data-driven decision-making and marketing strategies.
