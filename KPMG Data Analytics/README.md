## BACKGROUND

### Data Quality Assessment & Data Analysis
Sprocket Central Pty Ltd is a long-standing KPMG client whom specialises in high-quality bikes and accessible cycling accessories to riders. Sprocket Central Pty Ltd has approached Tony Smith (Partner) in KPMG’s Lighthouse & Innovation Team. They are keen to learn more about KPMG’s expertise in its Analytics, Information & Modelling team. 

Smith discusses KPMG’s expertise in this space (you can read more [here](https://kpmg.com/au/en/home/services/advisory/management-consulting/digital/data-analytics-modelling.html) ). 
In particular, he speaks about how the team can effectively analyse the datasets to help Sprocket Central Pty Ltd grow its business.

Primarily, Sprocket Central Pty Ltd needs help with its customer and transactions data. 
The organisation has a large dataset relating to its customers, but their team is unsure how to effectively analyse it to help optimise its marketing strategy. Their marketing team is looking to boost business by analysing their existing customer dataset to determine customer trends and behaviour.

However, in order to support the analysis, you speak to the Associate Director for some ideas and 
she advised that *the importance of optimising the quality of customer datasets cannot be underestimated. 
The better the quality of the dataset, the better chance you will be able to use it drive company growth.*

The client provided KPMG with 3 datasets:
- Customer Demographic 
- Customer Addresses
- Transactions data in the past 3 months

[Check the datasets.](https://github.com/eunikehp/Forage-Virtual-Internship/blob/main/KPMG%20Data%20Analytics/KPMG%20raw%20data.xlsx)
  
You decide to start the preliminary data exploration and identify ways to improve the quality of Sprocket Central Pty Ltd’s data.

Tips: Raw data fields may be transformed into other calculated fields for modelling purposes (i.e. converting D.O.B to age or age groups).  Tips: You may source external data from the ABS / Census to add additional variables that may help support your model. 

 

## TASK
1.  Assess the quality of their data.
2.  Make recommendations on ways to clean the underlying data and mitigate these issues.
3.  Recommend which of these 1000 new customers should be targeted to drive the most value for the organisation.

## STEPS
1.  Data cleaning (Finding issues and recommendations)
2.  Understanding the data distributions
3.  Feature engineering
4.  Data Exploration
5.  Model Development (data transformations and modelling)
6.  Interpretation (result interpretation and reporting)

## ISSUES & RECOMMENDATIONS

After reviewing the datasets from Sprocket Central Pty Ltd, I found there are some data quality issues and methods to mitigate data inconsistencies. That is followed by the recommendations to avoid the reoccurrence of data quality issues:
1. Inconsistent values for the same attribute (e.g. Male being represented as "F", "Femal" and "Female". New South Wales being represented as “NSW” and “New South Wales”).
*Mitigation*: To ensure consistency, I used regular expression to replaced extended values into abbreviations.
*Recommendation*: Better use a drop-down list rather than a free text field for entering the data .
*Actions*: The data has been cleaned to avoid multiple representations of the same value. Gender records ‘U’ have been replaced based on the distribution from the dataset.

3. Inconsistent data type for the same attribute (e.g. numeric values for some fields and strings for others) 
*Mitigation*: Convert selected records in characters to numeric. Remove non-numeric characters from string. *Recommendation*: Ensure that fact tables in the given database have constraints on data types. 
Having different data types for a given field makes it difficult to interpret results at a later stage. Therefore, appropriate data transformations are made to ensure consistent data types for a given field.

4. Empty/missing values in certain records of some columns, such as brand, job_title, and job_industry_category.
*Mitigation*: Filter out the record entirely from the dataset if only a small number of rows are empty. But, if it is a core field, impute based on distribution in the dataset. 
*Action*: For key datasets, such as transactions, less than 1% of transactions (totalling less than 0.1% of revenue) have missing fields. These records have been removed from the dataset.

5. More customer_ids in the ‘Customer Address table’ rather than in 'Customer Demographic’ and ‘Transactions table’ 
*Mitigation*: Ensure all tables are from the same period. Only customers in the Customer Demographic dataset will be used as a dataset for our model. 
*Action*: The data received may not be in sync with each other which may skew the analysis results if there are missing data records. List of outliers will be saved in the Excel file ‘data_outliers.xlsx’.


 

