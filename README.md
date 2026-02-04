# <center>Mobile Big  Data Analytics & Management - Assignment 1</center>

This code and summary can be accessed at [https://github.com/Onitsiky/MBD-Assignment-1](https://github.com/Onitsiky/MBD-Assignment-1)

## Context
This README explains the approaches used, decision made and the key findings from analysing and exploiring the dataset [Mobile phone activity in a city](https://www.kaggle.com/datasets/marcodena/mobile-phone-activity) from Kaggle, which consists of CDR data from the city of Milan and the Province of Trentino (Italy).

## Task 1: Load and Merge Data
### 1. Loading SMS/Call/Internet activity data
Here pandas was used to import 3 different csv files (*sms-call-internet-mi-2013-11-02.csv, sms-call-internet-mi-2013-11-04.csv and sms-call-internet-mi-2013-11-06.csv*), which then where combined in a unique dataframe. 
#### 2. Creating a clean analysis-ready dataset
Some numerical columns (*smsin, smsout, callin, callout, internet*) presented empty and missing values in some records, so to avoid future complication during the analysis, these missing values where replaced by the mean of each column.

Several columns where added to the initial dataset:
- *date, time and hour* columns where separated for better classification later
- *total_sms, total_calls, total_internet* columns where added to get the sumation of each sms, call and internet rate for each records

## Summary of the key findings
The combined dataset contained a total of 6564031 records, from 10000 different grid cells, and about 302 different country codes.

The missing values where mostly from the columns *smsout* and *callin*, but the other ones contained missing values too. And in total, in order to fill those empty values and get a cleaner dataset, 5880441 records have been modified.

From the analysis too, it was discovered that calls, sms and internet activities mostly reached its peak at around **5:00 p.m**, and the lowest rate usually occurs around **4:00 a.m**, and almost 3/4 of the activities happens during daytime.

About the activity directions, we can note the following: 
- most of the call are Incoming international ones
- and same for the sms activities (mostly international)

And at the end, it was also found that the call and sms activities are moving together: if calls are increasing, then so do for the sms too.