# Introduction
My names Bobby and this is another case study that I will be anaylzing for you guys, I am still practicing coding In R so bare with me
You can follow me step by step or EMAIL me @CHIENG@LIVE.CA if you have any questions.

# About the Data 
This dataset contains 11 columns and they are:

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
1. Download the CSV file from Kaggle [Data Science Salary](https://www.kaggle.com/datasets/arnabchaki/data-science-salaries-2023)
2. Extract CSV to specific folder - My folder is called "Salary_Data"
3. Open up R Studio Desktop and 
4. setwd("C:/Users/Bobby/Desktop/Data_Salary") or import manually
5. Install packages required such as 'Tidyverse', 'ggplot2', 'dplyr', and 'table.data'



# Process

Lets see the different variables and rows of our current data set by using str, head or even glimpse from the dplyr package!

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

Next lets clean this dataset so we can analyze it further
Lets check for missing or invalid values
```R
is.na(ds_salaries)

work_year experience_level employment_type job_title salary salary_currency salary_in_usd employee_residence
   [1,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [2,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [3,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [4,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [5,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [6,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [7,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [8,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
   [9,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
  [10,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
  [11,]     FALSE            FALSE           FALSE     FALSE  FALSE           FALSE         FALSE              FALSE
  ```
As far as I understand, FALSE = no missing values
TRUE = missing values
We can move on

Lets recheck our collums
ls(ds_salaries)
```r
 [1] "company_location"   "company_size"       "employee_residence"
 [4] "employment_type"    "experience_level"   "job_title"         
 [7] "remote_ratio"       "salary"             "salary_currency"   
[10] "salary_in_usd"      "work_year"         
```

Lets group the data in seperate data frames that we want to plot
I want to find out the highest paying salary with which job title so we should group them up

```r
salary_by_job <- aggregate(salary ~ job_title, data = ds_salaries, FUN = max)
```

salary_by_job <- salary_by_job[order(salary_by_job$salary, decreasing = TRUE)
