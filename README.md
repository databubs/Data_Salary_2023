# Introduction
My names Bobby and this is another case study that I will be anaylzing for you guys, I am still practicing coding In R so bare with me
You can follow me step by step or EMAIL me @CHIENG@LIVE.CA if you have any questions.

# About the Data 
This dataset contains 11 columns and they :

1)  work_year: The year the salary was paid.
2)  experience_level: The experience level in the job during the year
3)  employment_type: The type of employment for the role
4)  job_title: The role worked in during the year.
5)  salary: The total gross salary amount paid.
6)   salary_currency: The currency of the salary paid as an ISO 4217 currency code.
7)  salaryinusd: The salary in USD
8)  employee_residence: Employee's primary country of residence in during the work year as an ISO 3166 country code.
9) remote_ratio: The overall amount of work done remotely
10) company_location: The country of the employer's main office or contracting branch
11) company_size: The median number of people that worked for the company during the year

#  Data Set Up
1. Download the CSV file from Kaggle
2. Extract CSV to specific folder - My folder is called "Salary_Data"
3. Open up R Studio Desktop and 
4. setwd("C:/Users/Bobby/Desktop/Data_Salary") or import manually
5. Get all the packages required such as 'Tidyverse', 'ggplot2', 


# Process

Lets see the different variables we may see using head, str, and summary.

I started off with  str(ds_sarlies) to get a better understanding of the data.
```r
3755 obs. of  11 variables
$ work_year         : num  2023 2023 2023 2023 2023 ...
 $ experience_level  : chr  "SE" "MI" "MI" "SE" ...
 $ employment_type   : chr  "FT" "CT" "CT" "FT" ...
 $ job_title         : chr  "Principal Data Scientist" "ML Engineer" "ML Engineer" "Data Scientist" ...
 $ salary            : num  80000 30000 25500 175000 120000 ...
 $ salary_currency   : chr  "EUR" "USD" "USD" "USD" ...
 $ salary_in_usd     : num  85847 30000 25500 175000 120000 ...
 $ employee_residence: chr  "ES" "US" "US" "CA" ...
 $ remote_ratio      : num  100 100 100 100 100 0 0 0 0 0 ...
 $ company_location  : chr  "ES" "US" "US" "CA" ...
 $ company_size      : chr  "L" "S" "S" "M"
 
```



