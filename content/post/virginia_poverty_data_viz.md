+++
author = "Andrea Jackson"
title = "Poverty in Virginia Tableau Visualization"
date = "2021-01-16"
description = "Lorem Ipsum Dolor Si Amet"
tags = [
    "virginia",
    "tableau",
]
+++
##Poverty in Virginia 
#### data source: https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-2018-zip-code-data-soi 
#### Data cleaning done in Rstudio
Zip code data and percentages of joint tax filers that earn less than $25k were extracted and cleaned from the IRS website

### code:

```{r include = TRUE}

va_irs_data<-rename(X18zp47va)
#extract 3 columns
va_irs_data <-va_irs_data[,c(1,2,5),]
va_irs_data <-va_irs_data[-c(1:2),]
#use first row as column names
names(va_irs_data) <- va_irs_data[1,]
#remove first 11 rows
va_irs_data <-va_irs_data[-c(1:11),]

#remove na values
va_irs_data<- na.omit(va_irs_data)

#change number of returns from character to numeric 
va_irs_data$`Number of joint returns`<-as.numeric(as.character(va_irs_data$`Number of joint returns`))

#create an income percentage column based on zip code

#install zoo
#install.packages("zoo")
library(zoo)

#create a rolling sum for percentages
va_irs_data$zip_sum <-rollsum(va_irs_data$`Number of joint returns`, k= 6, align = 'left', fill = NA)
#extract row for $25k
low_income_va <- va_irs_data[seq(1, nrow(va_irs_data), 6), ]
#search data type
str(low_income_va$zip_sum)
str(low_income_va$`Number of joint returns`)
#change data types to integer to divide and make proportion
low_income_va$`Number of joint returns`<-as.integer(as.numeric(low_income_va$`Number of joint returns`))
low_income_va$zip_sum<-as.integer(as.numeric(low_income_va$zip_sum))

#create proportion of low income residents in a column
low_income_va$low_income_percentage <- low_income_va$`Number of joint returns`/ low_income_va$zip_sum

names(low_income_va)[1]<-"zip_code"
low_income_va_zip <-bind_cols(low_income_va$zip_code,low_income_va$low_income_percentage)
names(low_income_va_zip)[1]<-"zip_code"
names(low_income_va_zip)[2]<-"low_income_percentage"

```
### Tableau visualization
![virginia_map](/images/low_income_va.png)

<div style="align: center; margin-left: -150px;"> <iframe src="https://public.tableau.com/views/low_income_va/Dashboard1?:showVizHome=no&:embed=true" width="1000px" height="900px" frameborder="0"></iframe> </div> 


