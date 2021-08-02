# Taxi-Cab-Data-Analysis-and-Insights
Data analysis and Insights generations to determine which taxi cab company to invest in.

Link for the streamlit app: <https://house-rocket-insight-project.herokuapp.com/>

![alt text](https://github.com/IgorQueiroz23031988/House-Sales-Data-Anaysis-and-Insights/blob/main/HOUSE%E2%80%99S%20BUY%20AND%20SALES%20DATA%20ANALYSIS%20AND%20INSIGHTS.png)

## 1. Business Problem/Understanding.

XYZ it is a private firm located is US. Due to remarkable growth in the Cab Industry in last few years and multiple key players in the market, it is planning for an investment in Cab industry and as per their Go-to-Market (G2M) strategy they want to understand the market before taking final decision. 

The object of this project is providing answer of the main questions made by the company’s CEO, which are:
 
*	Which Cab companies XYZ firm should invest, in general?
*	What is maximum amount of money made by each company? 
*	Which company provided more taxi travels?
*	Which company has more customers?

 Also there are secondary questions that could help the CEO decision, which are?
 
*	Which area of US the Cab companies provide higher incomes and taxi travels?
*	Which season of US the Cab companies provide higher incomes and taxi travels? 

The answer for those questions is presented in two different methods:
 
*	Reports recommending which Cab company The firm XYZ should invest.
*	A website created by the data analyst showing a table of which company has the higher amount of taxi travels, profit and customers. Also a collection of hypotheses and a dashboard is presented in order to auxiliary the CEO decisions.
 
The tools used for this project are: Python 3.8, Pycharm, Jupyter Notebook, Streamlit and Heroku.

## 2. Data Understanding.

There are 7 different datasets provided: <https://www.kaggle.com/nishantdhingra/cabs-fare-data>.

* Cab_Data.csv – this file includes details of transaction for 2 cab companies;
* Customer_ID.csv – this is a mapping table that contains a unique identifier which links the customer’s demographic details;
* Transaction_ID.csv – this is a mapping table that contains transaction to customer mapping and payment mode;
* City.csv – this file contains list of US cities, their population and number of cab users.
* States – this file contains list of US cities, regions and divisions. – provided by website: <https://www.kaggle.com/omer2040/usa-states-to-region>
* US-federal-holidays-2011-2020 – this file contains list of US holidays from 2011 to 2020. – provided by website: <https://data.world/sudipta/us-federal-holidays-2011-2020#>
* Us-states.json


 Dataset list:
 
Attributes |	Meaning
---------- | ----------
Transaction ID         |	Unique ID for each cab service
Date of Travel       |	Date of travel by the user on cab
Company      |	Name of the cab company
City   |	City of the cab travel
KM Travelled	 | KM Travelled made in each travel
Price Charged |	Price charged plus tax – Total charged
Cost of Trip |	Price Charged for the travel
Customer ID |	Customer ID
Gender |	Customer gender
Age |	Customer Age
Income (USD/Month) |	Customer Income 
Payment_Mode |	Payment method
Population |	Each city population
Users |	 Cab users by city
State |	US State
State Code |	US state code
Region |	US region
Division |	US division
Date |	Date of holiday
Holiday |	Holiday name

## 3. Business Assumptions.

For further analysis, it is necessary to know the period of time of each season on US, those information will be included in a variable called Season. According to the website: <https://www.timeanddate.com/calendar/aboutseasons.html>, each season is specified on the followed days:
 
*	spring runs from March 1 to May 31;
*	summer runs from June 1 to August 31;
*	fall (autumn) runs from September 1 to November 30; and
*	winter runs from December 1 to February 28 (February 29 in a leap year).

Due the dataset City.csv does not inform the State of two cities: SILICON VALLEY and ORANGE COUNTY, it is necessary specify the States of them.
According to the website: <https://www.britannica.com/place/Silicon-Valley-region-California>, The SILICON VALLEY State is California, CA.
Also according to the website: <https://en.wikipedia.org/wiki/Orange_County,_California>, The ORANGE COUNTY State is California, CA.


## 4. Solution Strategy.

As the company’s CEO wants answer for two different questions, the solution strategy is divided into 2 parts:<br/><br/>


* __First part:__ Which houses to buy?
 
1º - Collect data from kaggle’s website.
 
2º - Group them by region (zipcode), due this attribute is extremely influential on the house’s price.   
 
3º - Find the house’s price median by region.
 
4º - Recommend that the houses with prices inferior to the median value should be bought, and the condition is minimal 3.  
 
5º - Filter those houses, that should be bought, by size, number of floors, number of bedrooms, and number of bathrooms, in order to identify the level of recommendation of each house.<br/><br/>
 
 
* __Second part:__ When to sell the houses and for how much?
 
__1º__ - After the company buys the houses, the data is grouped by region and seasons.
 
__2º__ - Inside each region and seasons, it is calculated the median price.   
 
__3º__ - If the buy price is higher than median price plus season and recommendation to buy is regular, than the sell price will be equal the buy price plus 10 %. 
 
   If the buy price is higher than median price plus season and recommendation to buy is high, than the sell price will be equal the buy price plus 12.5 %.
 
   If the buy price is higher than median price plus season and recommendation to buy is very high, than the sell price will be equal the buy price plus 15 %.
 
   If the buy price is lower than median price plus season and recommendation to buy is regular, than the sell price will be equal the buy price plus 30 %.
 
   If the buy price is lower than median price plus season and recommendation to buy is high, than the sell price will be equal the buy price plus 37.5 %.
 
   If the buy price is lower than median price plus season and recommendation to buy is very high, than the sell price will be equal the buy price plus 45 %.
 
__4º__ - It is specified the best moment to sell based on the profit by season.
 
__5º__ - It is specified the best moment to sell based on the profit by season and recommendation to buy in general and individual houses.
 
__6º__ - It is specified the total profit by buying and selling houses.
 
## 5. Top 08 Data Insights.

__Hypothesis 01:__ Houses which has water view are 20% more expensive, in general.

__False:__ Houses with water view are 212.57668803323867 percent more expensive.<br/><br/>


__Hypothesis 02:__ Houses that was built before 1955 are 50% cheaper, in general.

__False:__ Houses that was built before 1955 are -0.7757205525248732 percent cheaper.<br/><br/>


__Hypothesis 03:__ Houses without basement are 40% bigger them house with basement, related to total area (sqft_lot). 

__False:__ Houses without basement are 22.483151526642544 percent bigger them houses with basement.<br/><br/>


__Hypothesis 04:__ The growth of house prices YoY (Year over Year) (May 2014 compared to May 2015) is 10%, in general. 

__False:__ The total houses price YoY (Year over Year) suffered a decrease of -62.79177358882806 percent.<br/><br/>


__Hypothesis 05:__ Houses with 3 bathrooms have a growth MoM (month over Month) of 15%.

__False:__ The total houses price MoM (month over Month) suffered a decrease of -9.953899240174858 percent.<br/><br/>


__Hypothesis 06:__ Houses with number of bedrooms above 8 have a number of bathrooms 40% higher than houses with number of bedrooms between 5 and 8, and 94% higher than houses with number of bedrooms between 1 and, 4 on average.

__True:__ Houses with number of bedrooms above 8 have a number of bathrooms 39.9514563106796 percent higher than houses with number of bedrooms between 5 and 8, and 94.48676155875182 higher than houses with number of bedrooms between 1 and 4.<br/><br/>

__Hypothesis 07:__ Houses with 7 bedrooms has the total area (sqft_lot) bigger between 132 to 320 percent than houses with 8 to 11 bedrooms, on average.

__True:__ Houses with 7 bedrooms has the total area (sqft_lot) bigger between 132.29431644290653 and 320.17243208828523 percent than houses with 8 to 11 bedrooms.<br/><br/>


__Hypothesis 08:__ Renovated Houses have living rooms 12% bigger than houses not renovated, on average.

__True:__ Renovated Houses have living rooms 12.132344286788795 percent bigger than houses not renovated, on average.

## 6. Financial Results.

 House Rocket Company would have a profit of almost 19 percent, which are more than $771 million, if applies this data analytics method.

## 7. Conclusion.

In conclusion, it is possible to identify that the application of data analytics project at dataset from House Rocket Company was very successful, providing a huge profit opportunity based on which houses to buy and when to sell.

## 8. Next Steps.

Other project that can be made with this dataset is the exploration data analyses, which identify the best’s attributes in order to apply machine learning algorithms, with the objective to predict the price of futures houses to buy.



