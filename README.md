# Kickstarter-Analysis
Performing an analysis on Kickstarter data to uncover trends
## Overview of Project
This analysis was conducted to further understand Kickstarter campaign data.

### Purpose
The purpose of this analysis is to understand the relationship between theatre play campaign outcomes, the launch dates of the plays, and their funding goals. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

This analysis was performed to understand the relationship between launch date of Kickstarter campaign and their outcomes (whether campaigns were successful, failed, or were canceled). 

To perform this analysis:
1.	Created a Pivot Table in a new worksheet (“Theatre Outcome by Launch Date”) using data from the Kickstarter_Challenge.xlsx worksheet.
2.	Filtered Pivot Table to include the “theatre” Parent Category and campaign launch year.
3.	Tabulated “successful” ,”failed”, and “canceled” outcome counts by months of the year when the Kickstarter campaign launched.

When performing this analysis, the only challenge I encountered was filtering by “Years”. While I created a new variable using the =YEARS() function to extract the launch date year from the launch date variable, I did not use that specific variable to filter the PivotTable. Instead, I filtered using the “Date Created Conversion” variable (date converted to Excel from Unix Timestamps).

### Analysis of Outcomes Based on Goals

This analysis was performed to understand the relationship between Kickstarter campaigns funding goals and their outcomes (whether campaigns were successful, failed, or were canceled).

To perform this analysis:
1.	Created new sheet “Outcomes Based on Goals” with the following columns to hold the data: Goal, Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, Percentage Canceled.
2.	These new rows were tabulated by the following fundraising goal ranges: 

![image](https://user-images.githubusercontent.com/93107507/141716659-0af93e06-7afa-4884-bb9d-456f8b03ecab.png)

3.	Used the =COUNTIFS() function to count the corresponding outcomes per cell:

-i.e.,  =COUNTIFS(Kickstarter!$O:$O,"plays",Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<=4999") to count the number of plays whose fundraising was successful and had a fundraising goal between $1000 and $4999.

5.	After each goal had been tabulated per successful, failed, and canceled outcomes, I summed the total count of plays by fundraising goal using the =SUM() function under the Total Projects column.

-i.e., There were 169 total plays whose fundraising goal was between $5000 and $9999

6.	Once the total projects count was estimated, I calculated the percentage of successful, failed, and canceled plays by dividing the outcome count per financial goal range by the total number of projects in the financial goal range.

-i.e, There were 12 plays whose fundraising goals was between $15000 and $19999. These 12 plays were 50% of the total plays whose fundraising goal was between %15000 and $19999.

### Challenges and Difficulties Encountered

A challenge I encountered was making sure the total number of projects equated the total number of plays found in the “Subcategory Statistics” sheet. Initially, I thought that the numbers did not add up. However, that sheet considers the number of plays with a “live” outcome. Once I did the arithmetic, subtracting the number of “live” plays from the total, the numbers added up to that of the total count In the “Outcomes Based on Goals” sheet.

## Results
When not considering a specific year, May had the highest number of successful and canceled campaigns. Coincidentally, both outcomes saw an upward trend starting 2 months prior, and a downward trend which lasted 5 months. The successful outcome in theatre trends follows the same trends in all of the overall trends. This trend may be due to the fact that theatre accounts for 33% of all categories. 

![image](https://user-images.githubusercontent.com/93107507/141716841-cf768792-5201-46e5-b84c-2a26ffeedb9b.png)
![image](https://user-images.githubusercontent.com/93107507/141716851-dd242764-a4b7-4689-9e3a-52a97384bc63.png)

In general, there were more successful campaigns counts than there were campaigns that failed, especially those whose campaign financial goals were less than $19999. The graph shows an inverse relationship between campaign success and failure. The less expensive a campaign is, the more likely it is to succeed. Conversely. The more expensive a campaign is, the more likely it is to fail.

![image](https://user-images.githubusercontent.com/93107507/141716951-0dff3774-1034-415e-b095-40904e7590e4.png)
 
### Limitations

While this data can be extrapolated, this data set does not include a season variable. This dataset is also heavily biased towards the theatre parent category, accounting for 33% of the total data in this dataset. While this does not specifically affect this current analysis, an analysis seeking to understand overall outcomes would lose nuance. 

### Other tables and graphs

Other tables we may want to create is one which displays/filters the outcomes based on goals by geography/country—this may help us understand which markets are more likely to have successful fundraising outcomes. Additionally, one that filters outcomes by season—my hypothesis would be that in winter months, people will be less willingly to be out In order to evade the cold.
