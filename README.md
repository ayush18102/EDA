CREDIT EDA CASE STUDY
Abstract In this case study, we are applying EDA in a real business scenario. Apart from applying the techniques, we are also developing a basic understanding of risk analytics in banking and financial services and understanding how data is used to minimize the risk of losing money while lending to customers.
Introduction:
In the case study, there are three csv data sets were provided:
1.	Application data
2.	Previous application data
3.	Column

1.	APPLICATION DATA
First, we have to import CSV data file i.e. Application data for our analysis. This contains all the information of the client at the time of application.
 Reading a CSV file there is 307511 rows and 122 columns
By checking shape, we can also get the same rows and columns 
Most of the columns are of integer or float by “application.info(“all”)”.  And application. dtypes.values_counts() below I am attaching a screenshot






After reading all the files the next step is for data cleaning:
DATA CLEANING
Data cleaning is necessary for preparing data for analysis. The following steps are taken for Data cleaning:
1.	Check the sum for all the null values by application. describe().T
 

2.	Finding out null values in each column.
 

3.	Percentage of null values in each column
 

4.	Dropping columns where null values are more than 18%
 
5.	Checking the shape of the file by application. shape
 
Here now the number of columns is reduced to 38
6.	After removing null values there is some null value remaining only .20 which can be done by  filter 
A filter is done by putting value in true i.e 0
 
7.	Here I see that there are some null values present in ‘Name_type_Suite’. So I check if there are null values present or not then after that I filter that part.
8.	After that I make outlier
OUTLIER:
An outlier is an observation that lies an abnormal distance from other values in a random sample from a population.
Below some values are spotted as outliers with the help of plots.  
For the below plot of ‘CNT_CHILDREN’, we see that there is an Outlier. Since a family cannot or very rarely have 19 children.   
       

 For ‘DAYS_EMPLOYED’, we also find outliers at a range of 36,000. This is not possible. We can assume that this error occurred during data entry.
 

For plot ‘AMT_INCOME_TOTAL’, we can visually see that the MAX amount is way larger than the other statistical data Mean of 25,50,75 percentiles.
 

Above three outlier data described after describing that data, we make a graph differently.
 
Removed them and plotted them again to observe the difference.
Counting of children to a maximum value of 3.
 

The Number of Days employed so that we do not get highly distributed values:
 

The total amount of income, so that we do not get a highly distributed value. 
 
Furthermore, we have done some modifications to values, to make our analysis of data easier. We have taken the below two steps.
 
And then some binning of salaries done into high, medium and moderate for more clarity and make some plot also.
 
 
 
APPLICATION ANALYSIS:
1.	In analysis found that there is 3 gender i.e Male, female and XNA
 

This graph is shown that Males, females, and XNA but the male gender taking loans is not greater than the female gender in the entire population. 
From the above Plots and Data, it is visible that the Female clients are a better TARGET as compared to the Male clients.
2.	Now we analyse the salary Category, and flag work phone by making a plot.
 
In the above graph, it’s shown that A client with an extremely low salary has more chance to be a Defaulter when he did not provide a home phone number. Here approximately 30% of people only provided their phone number. 
3.	Salary vs Client whose Permanent Address does not match with Contact Address -Region Level 
When the Client gets an Extremely lower salary and his/her address does not match, then there is a Higher chance for him/her to be a defaulter.

4.	INCOME TYPE
Income vs Number of family members.
In the Above graph, People who get income via Maternity Leave tend to be more Defaulter when they have more Family Members.

5.	Distribution of organization type (Target 0)
 
From the plot points to be concluded:
	Clients of the organization type ‘Business entity type 3’, ‘self-employed, ‘others’, ‘Medicine’, and ‘Government’. Are most likely to pay the loan annuity on time.
	Clients from industry type 8, type 6, type 10, religion and trade type 5, and type 4 are more likely to default.

6.	Distribution of organization type (Target 1)
 
	As compared to the clients with NO payment difficulties, clients with payment difficulties have the 'construction' business type in the top 5 count replacing the 'medicine' business type.
	Most of the business types are the same as clients with NO payment difficulties, except we have the business type 'Transport: type1' in the case of clients with payment difficulties which wasn't present before.

7.	Distribution of clients with difficulties and all other cases:


8.79% (18547) out of the total client population (192573) have difficulties in repaying loans.

2.	PREVIOUS DATA 
•	Reading CSV file previous data.
 

There are 37 columns and 1670214

•	Previous data shape:
 

•	Checking the null values in percentage:

 


•	After cleaning null values and dropping values we get:

 



•	Now checking the percentage of loan status:

 

Making Loan status percentage pie chart:























•	After making a pie chart now have to check the type of client in percentage value:


 







Making a pie chart of client type you can see easily and understand well.
 

•	Now checking a contract type percentage of values.

 
In these, there are three contract types of loan:

	Cash loans
	Consumer loans
	Revolving loans
 


Above Making a pie chart for these three contract-type loans.

•	Now make a plot of the purpose of the loan name and their percentage values:
 


Most of the loan is taken for repairs.



•	Most loan people take cash as a mode of payment below I am showing a plot for this:

 

•	The primary reason for the loan rejected is not recorded HC followed by LIMIT below is graph:
 

•	There are some good category people who pay their loan on time below I am attaching some table and graph for this:

 
 

•	Most people acquire credit cards and cash from the bank. Their percentage is 40% as compared to another channel type below I am showing table and graph for this:

 


 




Merging both Data file Application data and previous data:

Both data are merged and now check both data relation and charts. After merging both data there is null values which has been removed.

 

After cleaning and filtering the data there are some charts:

•	Distribution in Contract types in data (Combined dataset).

 
High both Cash loans and consumer loans percentage is 44% while revolving loans 11% 

•	Gender distribution in combined datasets.

In these data set female category is loan high compared to the male. Male category is 32% while the female category 68% below is graph distribution of gender.
 

•	Correlation of target 0 and target 1

The correlation of target 0 is actually a repayer data and target 1 is defaulter:
	Target 0 data :
	Target 1:

Above both data is the same but difference is only the decimal point value defaulter payer more as compared to repayer data.

Also seen that online and amount credit taken more loans.
A loan-taken income type pays their loan on time.

Even here also the same variables, as we have seen in our application data, have been contributing more to the DEFAULTERS Identification.



 	Conclusion:
We have understood and gained insight into the data set i.e. performed an exploratory data analysis. I have learnt in this case study:
	I have extensively covered pre-processing step required to analyse data.
	I have done null value percentage and done cleaning, and filtered data.
	I have shown the necessary data which is helpful for analysing the data.
	In this data set, I have seen that most loans are taken in cash as a mode of payment.
	In this data set, I have seen that most of the repeaters taking loans have no refreshed loans and no new people taking loan.
	In this data set, I have also seen that most of the female category taken loans.
	That salary high take huge amount of loan and also saw that only 60 % to 65% only get approved remaining not getting their people cancelled their loans. And most effective there are some defaulter who not pay their loan on time.

Thank you
Prepared by Ayush Kumar Singh.

