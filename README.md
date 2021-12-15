# Data-512-Final-Project

# Abstract
The goal of this project is to understand the impact of vaccination on COVID in DuPage County, IL. I feel this is interesting and also important to know the number of cases increases as people take vaccines, to see the effect of vaccine and how far it is protecting people.
The project was divided into 4 parts:

Assignment A4: A Common Analysis where we do our base analysis on the Mask Mandate data of Illinois Dupage County and Confirmed Cases in the Dupage County.
Assignment A5: Extends the A4 analysis,  through the lens of human centered data science. In my analysis, I uses the Vacciation Data for the same county.
Assignment A6: Presentation.
Assignment A7: Final Report.

# Research Question and Analysis
The questions I am trying to answer from this Extension Plan is:

Does vaccination has any effect on covid.
Also, by using Statistical Methods like Multiple Linear regression I want to check how significant is the Vaccination data of different age groups in the county (As mentioned in the dataset).
The basic question I want to research is to check trends in covid based on vaccination in the county using visualization. (Whether it increases or decrease with time), I want to see the visualization of the county vaccination based on different age groups, which may support the regression analysis.


# Data Sources
To perform the analysis I will use the following different datasets.

1. The RAW_us_confirmed_cases.csv file from the Kaggle repository of John Hopkins University COVID-19 data - https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv
2. Mask Mandate Dataset - https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i
3. The Vaccination Dataset - https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-County/8xkx-amqh

The data set is large and has 32 columns and 1.09M rows.
The columns in the data set are Date, FIPS, Country of Residence, State of Recipient, etc. the detailed list of 32 columns is found in the dataset link. Below is the table of the columns which I want to use in this scenario.

**Column Names:**
Date
FIPS
Series_Complete_pop_Pct(totoal population percentage)
Recip_County(CountyName)
Recip_State(state Name)
Series_Complete_yes(Total population got vaccinated)
Series_Complete_12Plus (population above !2+plus who got vaccinated)
Series_Complete_12Pluspop_Pct (percentage of 12+ population who got vaccinated)
Series_Complete_18Plus (18+ population who got vaccinated)
Series_Complete_18PlusPop_pct (Percentage of 18+ population)
Series_Complete_65Plus (65+ population who got vaccinated)
Series_Complete_65PlusPop_Pct (percentage of 65+ population who got vaccinated)
Metro_status (If it is a metro or non-metro)


# Methodology

### Correlation between covid cases and housing prices 
Here I will perform exploratory data analysis by creating visualizations to see the correlation between housing market data and covid cases week over week.  

Here I will plot the following visualization from the redfin data set. 
Weekly confirmed covid cases and the number of new listings.
Weekly confirmed covid cases and the total number of homes sold.
Weekly confirmed covid cases and inventory.
Weekly confirmed covid cases and median sale price.

 ### Multiple Linear Regression
I will also perform linear regression to predict housing prices for 2020 and 2021 and compare it with actual housing prices to see if there is a difference between predicted and actual housing prices for 2020 and 2021. 

Linear regression suits best to find the relationship between a dependent continuous variable (Median Sale Price) and one or more explanatory independent variables (Month/Year). Linear regression suits best here because we can see a linear trend in the dataset for housing prices and housing prices are normally distributed. 

![plot4](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/linearregression/median_sale_prie_mecklenburg_county.jpeg)

I will fit a univariate linear regression model using historical data from (2013- 2019)  where the feature is the monthly dates and the target is the median housing price. We are all aware of the housing market crash in 2007-2008 and it took the market some time to stabilize after the crash, hence I have decided to train the model with data post-2010.  I will split the data into (80-20 train test split) and fit a linear regression model using python scikit learn. I will also compute the RMSE (root mean square error) as a measure of model performance and use the model to predict housing prices for 2020 and 2021 and compare if the prediction is higher or similar to actual prices. 

![plot4](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/linearregression/linear_regression_line_median_sale_price.jpeg)

The model's performance on the test set is evaluated using the common evaluation metrics for regression problems
MAE, MSE and RMSE on Test Data for Mecklenburg

**Mean Absolute Error**: 9957.248703801895
**Mean Squared Error**: 163812031.95049974
**Root Mean Squared Error**: 12798.90745143896

![plot4](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/linearregression/test_set_actual_vs_predicted_price.jpeg)

# Summary Plots and Visualization

### Findings
 **Housing Inventory**: During the pandemic in 2020 and 2021, we can see a sharp decline in housing inventory (blue line) since January 2021(peak of covid) as seen on the red line. A decline in inventory was caused by multitude of reasons such as decline in new constructions due to supply chain disruptions, people not wanting to sell homes due to economic uncertainty, people not wanting to sell homes to avoid home visits by strangers to avoid contracting the virus, and also because of strict stay at home orders and lockdowns in place by the government. 
 
![plot1](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/correlation/weekly_cases_vs_house_inventory_mecklenburg_county.jpeg)

**Median Sale Price**:  We can see an upward trend in median housing prices overall in NC. The housing price dipped briefly around January 2021 when the cases peaked, but it steadily increased after that. We can see a 100K increase in median sale price in a span of roughly two years from 260k to 360k. The increase in Median Sale Price can be correlated to the decline in inventory as can be seen from the above graph. 

![plot3](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/correlation/weekly_cases_vs_median_sale_price_mecklenburg_county.jpeg)

**Total Number of Homes Sold and Total Number of New Listings:**  The graph on the left shows the fluctuations in the total number of homes sold.  We can see at the start of the pandemic the number of homes sold were lower as there was an overall uncertainty due to the pandemic. Around June 2020 we can see the number of homes sold start to increase and then it dips when the number of covid cases reaches its peak around January 2021. Similarly, we can see a sharp drop in the number of new listings around January 2021 when the cases peak. From these two graphs, we can conclude that everytime the COVID cases increase the number of homes sold and number of new listings in the market decrease. This could be caused by a number of factors like lockdown, fear among people of getting covid by doing home tours, sellers thinking they might not be able to sell at a high price if there are not enough buyers, real-estate agents not wanting to do in-person home tours etc. 

![plot2](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/correlation/weekly_cases_vs_houses_sold_mecklenburg_county.jpeg)

![plot4](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/correlation/weekly_cases_vs_new_listing_mecklenburg_county.jpeg)

### Linear Regression

From the output of the linear regression model, we can see that there is roughly 100K difference between the actual housing and predicted housing price for 2020 and 2021. The model was trained with historic housing price data from (2013 to 2019) and based on that was asked to predict the housing price for 2020 and 2021. The model output shows that the housing price during the pandemic increased significantly more compared to previous years and that houses sold for a higher price than they should have been.

![plot4](https://github.com/Poornima-Muthukumar/DATA512/blob/master/data-512-final-project/images/linearregression/actual_vs_predicted_price_validation_set.jpeg)

   | Year                        | % Change                               |
   |-----------------------------|----------------------------------------|
   | 2014                        | 0.026586                               |
   | 2015                        | 0.051282                               |
   | 2016                        | 0.131707                               |
   | 2017                        | 0.012931                               |
   | 2018                        | 0.089362                               |
   | 2019                        | 0.050781                               |
   | 2020                        | 0.222770                               |
   | 2021                        | 0.194801                               |

# Conclusion
Through my analysis, I can conclude that the COVID-19 pandemic had an impact on the housing market in Mecklenburg County. We can see that COVID-19 pandemic has impacted both supply and demand in the housing market.  People wanted to take advantage of lower mortgage rates which caused the demand for housing to go up.

However the pandemic also fueled a shortage in supply of homes - both newly built and those sold by existing owners.  We can see a decline in housing inventory, number of new listings on the market as covid cases increased.  Thus we can conclude that an increased demand and a shortage in supply fueled the median sale price of the homes to go up throughout the pandemic. 

To conclude, this study informs the reader of their understanding of human centered data science as it is important to pay attention to this trend and for the government to take action. It is important to fix this gap between supply and demand by building more homes where people need it, otherwise this inequality will continue to skyrocket and a growing number of Americans will be shut out of the housing market altogether.

# Limitations
1. All my analysis and conclusions are based on Single Family Homes (SFH). This could mean that there could be other patterns and trends for different property types and my results do not extend to other residential properties such as condos, townhomes, etc
2. In my interest rate analysis, I focus on the 30 year fixed interest rate. This could mean that other interest rates could have influenced the housing market differently which is not explored in my analysis. 
3. The analysis uses a 7 day rolling average number of covid cases to see correlation between the number of covid cases and housing market and does not include deaths. 
4. The Redfin weekly and monthly data is not seasonally adjusted. Doing so could yield slightly different results. 

# Future Work
Future Work
1. It will be interesting to build on top of my analysis to see patterns in the housing market related to other factors such as work from home, commuting patterns, supply chain disruptions, wood prices, lockdown restrictions that have also had some impact on the housing market indirectly.
2. Another interesting future work is to see how the housing market performed in different states and counties and if there was any commonality that can be extended from such an analysis to generalize the results with similar size states and counties.
3. Another potential analysis involves how rental prices fluctuated throughout the pandemic and if there was any correlation between rental price and housing prices.
4. Another analysis that can be built on top of this includes looking at the median household income of the people purchasing the homes to further analyse how the government can create schemes to help racial and generational inequality. 
5. Going forward it would also be useful to put this visualization in a dashboard that gets refreshed with data on a day-to-day basis so we can see how the housing market evolved as COVID and its variants and cases change on a timely basis. 


# License
  My research would be released under an MIT License and the data is all public domain.

# Folder Structure
```
.
├── README.md
├── data_processed
│   └──covid-data-mecklenburg-cleaned.csv
|   └──housing-data-mecklenburg-cleaned.csv
|   └──housing-covid-merged.csv
├── data_raw
│   └──CONVENIENT_us_confirmed_cases.csv
|   └──CONVENIENT_us_deaths.csv
|   └──MORTGAGE30US.csv
|   └──RAW_us_confirmed_cases.csv 
│   └──mask-use-by-county.csv
├── results
│   └── ProjectPresentation.pptx
|   └── Common-Analysis-Reflection.doc
|   └── Final-Project-Report.doc
├── src
│   └── poornima-muthukumar-a4.ipynb
|   └── poornima-muthukumar-final-project.ipynb
├── images
|   ├──commonanalysis
|   |    └── 7Day_Average_Deaths_Mecklenburg_North_Carolina.jpeg 
|   |    └── Cumulative_Cases_Deaths_Mecklenburg_North_Carolina.jpeg
|   |    └── Mecklenburg-County-NC-Cumulative-Cases.jpeg 
|   |    └── Mecklenburg-County-NC-Rate-Of-Infection.jpg
|   ├──linearregression
|   |    └── median_sale_prie_mecklenburg_county.jpeg
|   |    └── linear_regression_line_median_sale_price.jpeg
|   |    └── test_set_actual_vs_predicted_price.jpeg
|   |    └── actual_vs_predicted_price_validation_set.jpeg
|   └──correlation
|   |    └── weekly_cases_vs_house_inventory_mecklenburg_county.jpeg
|   |    └── weekly_cases_vs_houses_sold_mecklenburg_county.jpeg
|   |    └── weekly_cases_vs_median_sale_price_mecklenburg_county.jpeg
|   |    └── weekly_cases_vs_new_listing_mecklenburg_county.jpeg
└── LICENSE

```
# Libraries Used:
1. pandas
2. numpy
3. json
4. requests
5. matplotlib


# References
  1. Federal Reserve Bank of St. Louis. (2021, December 9). The impact of covid-19 on the residential real estate market: St. Louis Fed. Saint Louis Fed Eagle. Retrieved December 11, 2021, from https://www.stlouisfed.org/publications/regional-economist/fourth-quarter-2020/impact-covid-residential-real-estate-market. 
   2. Demsas, J. (2021, February 5). Covid-19 caused a recession. so why did the housing market boom? Vox. Retrieved December 11, 2021, from https://www.vox.com/22264268/covid-19-housing-insecurity-housing-prices-mortgage-rates-pandemic-zoning-supply-demand. 
  3. Sai Balasubramanian, M. D. (2021, December 10). The COVID-19 pandemic has fueled a crisis in the housing market. Forbes. Retrieved December 11, 2021, from https://www.forbes.com/sites/saibala/2021/04/27/the-covid-19-pandemic-has-fueled-a-crisis-in-the-housing-market/?sh=49f3de175928. 
4. Valkov, V. (2019, July 5). Predicting house prices with linear regression: Machine learning from scratch (part II). Medium. Retrieved December 11, 2021, from https://towardsdatascience.com/predicting-house-prices-with-linear-regression-machine-learning-from-scratch-part-ii-47a0238aeac1. 
5. Faressayah. (2021, August 5). Linear regression 📈 house 🏡 price 💵 prediction. Kaggle. Retrieved December 11, 2021, from https://www.kaggle.com/faressayah/linear-regression-house-price-prediction. 
6. The impact of coronavirus on the U.S Housing Market - Redfin. (n.d.). Retrieved December 11, 2021, from https://www.redfin.com/guides/coronavirus-housing-market-impact. 

# Human Centered Data Science Perspective
In my analysis, I have made an effort to address a variety of human-cenetered data science considerations including:

1. Licenses: I ensured that the research is licensed under a MIT license so others can use it.
2. Copyright: Appropriately citing sources of data, tools, and inspiration
3. Interpretability: Following a literate programming style to explain decisions made along the way that impact the final results of my analysis
4. Reproduciblity: Making my research reproducible by providing information about my environment, how I used the data, and where I received my data in addition to including my data in my repository so that anyone could run my notebooks to replicate my results
5. Interpretability: I hav used methods like Linear regression that are very transparent and easy to understand for the audience of the research. Also I have used visualisation to convey the informaion in a simple manner to promote this goal.




