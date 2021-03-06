# Data-512-Final-Project

# Abstract
The goal of this project is to understand the impact of vaccination on COVID in DuPage County, IL. I feel this is interesting and also important to know the number of cases increases as people take vaccines, to see the effect of vaccine and how far it is protecting people.
The project was divided into 4 parts:

Assignment A4: A Common Analysis where we do our base analysis on the Mask Mandate data of Illinois Dupage County and Confirmed Cases in the Dupage County.

Assignment A5: Extends the A4 analysis,  through the lens of human-centered data science. In my analysis, I use the Vaccination Data for the same county.

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

Note: For A4 Analysis or Methodology is written respective folder

# Methodology

### Find the trends of Vaccination in COVID in Dupage Illinois
I tried to find the trends in data by different visualizations, ie by seeing the relation between vaccines taken by different age groups people and the number of cases in the county.
The following are the visualization graphs, I plotted from the vaccinations data merged with the final data which we got from the Analysis of Mask Mandate and Illinois Data.


No. of confirmed cases vs percentage of people vaccinated.
No. of confirmed cases vs percentage of people vaccinated vs people who have taken one dose.
No. of confirmed cases vs percentage of 12 plus people vaccinated 
No. of confirmed cases vs percentage of 18 plus people vaccinated 
No. of confirmed cases vs percentage of 65 plus people vaccinated 
Few more trends along with date.

### Visualization results

From the graphs, I see that there is a decrease in the Confirmed Covid cases with an increase in vaccination. It was not a continuous decrease but when we see on bigger picture on overall scenarios there is a decrease in confirmed cases.
In the period 2021-08, we saw an increase in cases than 2021-07, but I think this can be my future work to explore more why in this period cases increased.
I see the same results for all the three age groups of people:12plus, 18plus, 65plus.

The graphs can be found in the link:

https://github.com/sindhumadhadi09/Data-512-Final-Project/blob/main/A6/Output/vaccine_trends_12Plus.png (12 Plus graph)

https://github.com/sindhumadhadi09/Data-512-Final-Project/blob/main/A6/Output/vaccine_trends_12Plus_1.png(12 plus along with date feature)

https://github.com/sindhumadhadi09/Data-512-Final-Project/blob/main/A6/Output/vaccine_trends_18Plus.png(18 plus along with date feature)

https://github.com/sindhumadhadi09/Data-512-Final-Project/blob/main/A6/Output/vaccine_trends_65Plus.png(65 plus along with date feature)

https://github.com/sindhumadhadi09/Data-512-Final-Project/blob/main/A6/Output/vaccine_trends.png(No of confirmed cases vs percentage of people vaccinated.)

https://github.com/sindhumadhadi09/Data-512-Final-Project/blob/main/A6/Output/vaccine_trends_1.png(No of confirmed cases vs percentage of people vaccinated vs people who has taken one dose.)


### Regression Analysis
I want to check the correlation of different age group of people vaccinated in our dataset, and their impact on the increase in Covid cases. 
I selected these 3 variables in the dataset for our analysis and checked whether they are statistically significant:
Series_Complete_18PlusPop_pct
Series_Complete_65PlusPop_Pct
Series_Complete_12PlusPop_Pct

Call :  lm(formula = DailyCases ~   Series_Complete_12PlusPop_Pct + Series_Complete_18PlusPop_Pct + Series_Complete_65PlusPop_Pct, data = data) 


### Regression Results

Based on p-values, if the p-value is less than alpha (0.05), then the variable is statistically significant.
So, from the model, all the variables are statistically significant. Changes in these variables result in the change of Cases Count.

Based on the sign of the coefficient, we get whether it has a positive or negative correlation between the variables and the Cases Count.

# Conclusions

From the graphs and regression, it is evident that with an increase in no of people taking vaccines there is a decrease in the case count in DuPage County.

Also, from the regression, we found that the data is statistically significant.


# Limitations
1. Few missing data points in the data are the current data set is from 12/13/2020 to 11/09/2021, our A4 common analysis is from February 1, 2020, through October 15, 2021.
2. So there is a gap in the period, I couldn???t find a dataset exactly matching this period. 


# License
  My research would be released under an MIT License and the data is all public domain.

# Folder Structure
```
.
????????? A4
??????? ????????? A4.ipynb
??????? ????????? A4_common_analysis.pdf
??????? ????????? Analysis_Output
??????? ??????? ????????? DuPage(Illinois)_daily_cases.png
??????? ??????? ????????? Dupage(illinois)dailyCases_on_mask_mandate.png
??????? ??????? ????????? Dupage(llinois)_Cummulative_with_mask_on_Date.png
??????? ????????? Data_Cleaned
???????     ????????? Dupage(illinois_cases).csv
???????     ????????? mergerd_data.csv
???????     ????????? number_of_daily_cases.csv
????????? A5
??????? ????????? A5_Extension_Plan.pdf
????????? A6
??????? ????????? A6.ipynb
??????? ????????? Covid\ Analysis.pptx
??????? ????????? Data_cleaned
??????? ??????? ????????? Dupgae_Vaccines_cleaned_data.csv
??????? ??????? ????????? Dupgae_Vaccines_data.csv
??????? ??????? ????????? Dupgae_Vaccines_merged_data.csv
??????? ??????? ????????? new
??????? ????????? Output
??????? ??????? ????????? vaccine_trends.png
??????? ??????? ????????? vaccine_trends_1.png
??????? ??????? ????????? vaccine_trends_12Plus.png
??????? ??????? ????????? vaccine_trends_12Plus_1.png
??????? ??????? ????????? vaccine_trends_18Plus.png
??????? ??????? ????????? vaccine_trends_65Plus.png
??????? ????????? Regression.rmd
????????? LICENSE
????????? README.md

```
# Libraries Used:
1. pandas
2. numpy
3. matplotlib
4. datetime


### Factors Considering Human-Centered Data science concepts
In my analysis, I have tried to address a variety of human-centered data science considerations:

1. Licenses: The project is Licences under MIT for others to use it.
2. Reproducibility: Making my analysis reproducible by giving the information about data source and analysis docs, to tell how to use them, showing the results and conclusions for users to check from their reproducibility.
3. Interpretability: I have used methods like Multiple Linear regression that are transparent and easy to understand for the users or audience.

# Issues
I wasn't able to upload the data_raw files to GitHub due to file size issues - instead, the data can be found in the following Link. https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-County/8xkx-amqh




