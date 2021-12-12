# kickstarter-analysis
## Overview of Project
Louis is trying to start a play "Fever" but needs to fundraise some money. She wants to use kickstarter but wants to know when she should make the kickstarter and the success rate based on goals. Historical data from plays on kickstarter was analyzed using excel. Outcomes based on Launch Date and Outcomes based on Goal Amount were visualized using excel.
## Analysis and Challenges
### Analysis
1. Filter data based on plays:

The category and subcaterogy column was separated into parent category and subcategory then filtered by the subcategory plays using text to columns under the data tab in excel. The data launched was converted from unix timestamp to mm/dd/yyyy format then the year was extracted. The following excel formula were used: 
```
=(((J2/60)/60)/24)+DATE(1970,1,1)
=YEAR(S2)
```
J column was the unix timestamp and S column was the conversion to mm/dd/yyyy.

![Kickstarter Data](https://github.com/eddieperez1/kickstarter-analysis/blob/main/screenshot%20of%20kickstarter%20data.png)

2. Find the number of outcomes based on launch date and goal amount

A pivot table was created to find the outcomes based on launch date. In the pivot table, Parent Category and Years was added to filter, Outcomes added to columns, Data Created Conversion added to Rows and Count of outcomes added to Values. The results of the pivot table were visualized in a line chart.

A new table was created to find the outcomes based on goal amount. In the table, the goals column was filled with ranges of different amounts. Then using countifs, the columns number successful, number failed, and number canceled were filled. For example,
```
=COUNTIFS(Kickstarter!D:D, "<1000",Kickstarter!F:F,"successful",Kickstarter!R:R,"plays")
=COUNTIFS(Kickstarter!D:D, ">=1000",Kickstarter!D:D,"<5000",Kickstarter!F:F,"successful",Kickstarter!R:R,"plays")
```
Then total projects were calculated then percentage successful, percentage failed, and percentage canceled were calculated. The results were visualized with a line chart.

3. Visualize the results

![Theater Outcomes Based on Launch Date](https://github.com/eddieperez1/kickstarter-analysis/blob/main/screenshot%20of%20theater%20outcomes%20by%20launch%20date.png)
![Outcomes vs Goals](https://github.com/eddieperez1/kickstarter-analysis/blob/main/screenshot%20of%20outcomes%20vs%20goals.png)
### Challenges
Challenges faced were verifying the results made sense. In order to make sense of the results, the results need to be checked. Since the data is in another sheet, the data was filtered the same way using filters and then the filtered data was counted. Thus the results can be verified. By verifying the results, errors and mistakes can be eliminated in the analysis.
