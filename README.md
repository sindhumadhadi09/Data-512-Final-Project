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

Also, by using Statistical Methods like Multiple Linear regression,I want to check how significant is the Vaccination data of different age groups in the county (As mentioned in the dataset).

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

Note:For A4 Analysis or Methodology is written respective folder

# Methodology

### Find the trends of Vaccination in COVID in Dupage Illinois
I tried to find the trends in data by diffrent visulizations, ie by seeing the relation between vaccines taken by different agae group people and the number of cases in the county.
The following are the vizulization graphs, I plotted from the vaccinations data megerd with the final data which we got from the Analysis of Mask Mandate and Illinois Data.


No of confirmed cases vs percentage of people vaccinated.
No of confirmed cases vs percentage of 12 plus people vaccinated 
No of confirmed cases vs percentage of 18 plus people vaccinated 
No of confirmed cases vs percentage of 65 plus people vaccinated 
Few more trends along with date.

### Visualization results
From the graphs I see that there is a decrease in the Confirmed Covid cases with incraese in vaccination.It was not continuous decrease but when we see on bigger picture on overall scenarios there is a decrease in confirmed cases.
In the period 2021-08 we saw increase in cases than 2021-07, but I think this can be my future work to explore more why in this period of time cases increased.
I see the same results for all the three age group of people :12plus, 18plus, 65plus.
The graphs can be found in the link:


### Regression Analysis
I want to check the correlation of  different age group people vaccinated in our dataset, and their impact on the increase in Covid cases. 
I selected these 3 variables in the dataset for our analysis and checked whether they are statistically significant:
Series_Complete_18PlusPop_pct
Series_Complete_65PlusPop_Pct
Series_Complete_12PlusPop_Pct

Call :  lm(formula = DailyCases ~   Series_Complete_12PlusPop_Pct + Series_Complete_18PlusPop_Pct + Series_Complete_65PlusPop_Pct, data = data) 


### Regression Results:

Based on p-values, if p-value is less than alpha (0.05), then the variable is statistically significant.
So,from the model all the variables which are statistically significant. Changes in these variables result in the change of Cases Count.

Based on the coefficients sign, we get whether it has a positive or negative correlation between the variables and the Cases Count.

# Conclusions:

Through my analysis, I can conclude that the vaccinations has effect on had an impact on the housing market in Mecklenburg County. We can see that COVID-19 pandemic has impacted both supply and demand in the housing market.  People wanted to take advantage of lower mortgage rates which caused the demand for housing to go up.

However the pandemic also fueled a shortage in supply of homes - both newly built and those sold by existing owners.  We can see a decline in housing inventory, number of new listings on the market as covid cases increased.  Thus we can conclude that an increased demand and a shortage in supply fueled the median sale price of the homes to go up throughout the pandemic. 

To conclude, this study informs the reader of their understanding of human centered data science as it is important to pay attention to this trend and for the government to take action. It is important to fix this gap between supply and demand by building more homes where people need it, otherwise this inequality will continue to skyrocket and a growing number of Americans will be shut out of the housing market altogether.

# Limitations
1.Few missing data points in the data are the current data set is from 12/13/2020 to 11/09/2021, our A4 common analysis is from February 1, 2020, through October 15, 2021.
2. So there is a gap in the period, I couldn’t find a dataset exactly matching this period. 


# License
  My research would be released under an MIT License and the data is all public domain.

# Folder Structure
```


```
# Libraries Used:
1. pandas
2. numpy
3. json
4. requests
5. matplotlib


# References

# Human Centered Data Science Perspective
In my analysis, I have made an effort to address a variety of human-cenetered data science considerations including:

1. Licenses: I ensured that the research is licensed under a MIT license so others can use it.
2. Copyright: Appropriately citing sources of data, tools, and inspiration
3. Interpretability: Following a literate programming style to explain decisions made along the way that impact the final results of my analysis
4. Reproduciblity: Making my research reproducible by providing information about my environment, how I used the data, and where I received my data in addition to including my data in my repository so that anyone could run my notebooks to replicate my results
5. Interpretability: I hav used methods like Linear regression that are very transparent and easy to understand for the audience of the research. Also I have used visualisation to convey the informaion in a simple manner to promote this goal.

# Issues
I wasn't able to upload the data_raw files to github due to file size issues - instead the data can be found in the following reference.




