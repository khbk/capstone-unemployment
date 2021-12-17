
## Project_5
#### van Possum group - Jordan Gates, Joomart Achekeev, Brian Kim

### Intro
Given a wide selection of topics to work on for the project 5, van Possum group (Joomart, Jordan and Brian) has selected the vital issue of unemployment. In an attempt to model a real life project the group members have decided to ignore the available datasets and collect raw, uneddited and uncleaned data from numerous sources. The collected data included maximum information possible on such topics as numer of police per capita, number of enterprises per capita, population breakdown per capita and other related topics. The data was collected by US county for 2010, excluding the 2008 presidential election results, that have been used to derive the democrat/republican percentage of local population.

We set a very optimistic goal before actually touching the project to determine is it possible to predict unemployment rate depending on the certain characteristics of a standalone county?

The project problem statement is as follows: What factors correlate with the unemployment and can they be used to predict the unemployment rate in a random US county? 

And as a consequence, by tweaking these factors would it be possible to influence the unemployment rate?

##### (parts of the readme are in the exact order how the python codebooks are to be executed)

### 01 Data loading and cleaning

Due to the fact that the data was extracted from various sources, around 4.2% of the data was so corrupted and was eveluated as impossible to use in the modelling, this data was droped. Other values have been imputed with average statewide data since the rows where they were located contained other important information that would help our models learn important dependencies. THe final dataset prepared for futher processing has 28 columns of which 3 are location data (state, county, population) and 1 is th target data - unemployment.

### 02 EDA
Working with the Eda of our data, we were able to visually show what our findings looked like. For example, we first looked at the correlation of the whole data. With this, we were able to tell, which columns might have more impact towards our target variable ‘unemployment_rate_2010’. There are few graphs that we took a look at in more detail. 

Few scatter plots we have shown how the Democratic votes in 2008 graphed generally in a positive trend while Republican votes graphed in a negative trend. We have also graphed the relationship between population in different counties and the unemployment rate. But, inn general, it did not give sufficient evidence that population has much to do with unemployment rate. Same goes for the crimes per capita and unemployment rate. 

One surprising data we found was how much liquor stores per 10,000 people lead to the the high employment rate. The number of liquor stores per 10,000 people inn counties with unemployment rate less than 5% was 2.06 liquor stores per 10,000. While counties with unemployment rate more than 15% had 0.78 liquor stores per 10,000 people.

### 03 Preprocessing and Feature Engineering

This is the part where it got challenging and interesting. The original data showed low scores (train: 0.4299, test: 0.3938, cross_val: 0.3593) while fully polynomial transformed dataset showed extreame variance with over 600 columns. This is where the team had an idea to nad create grid search analog for the linear model in terms of correlation percentages of the numeric columns. The model had nested double loop with sufficient code inside and took some time to run but yeilded better scores with indication of which column interaction will yeild better results in the linear regression model.
The final dataset with certain data interaction had 101 columns and was save for future use in the modeling step. 

### 04 Modeling
As the modelling process is faster then the previous steps where, the team decided to compare the basic Linear Regression and Neural Network Performance. Even though the amount of data was limited by 3015 rows, neural network performed significantly better.
    Linear Regression returned Test 0.4836, Cross_val 0.4572
    Neural Network returned Test 0.6344
Even though there where other models such as Linear regression on the original not preprocessed dataset, and linear regression on PCA tuned dataset, but given poor performance of these models they were not used to train second level model.

Second level Linear Regression model was hand fed train test split predictions from first level models and returned even better results Test 0.935, Cross_val 0.921 (the team was actually scared of the result and went through the whole code several times to eliminate the possible mistakes)

### Conclusion

Given a task to select a project, find data, and pick a model to train is a very broad task. I believe that real world data scientist face this only when they are working on individual projects, the constraints that are provided by the employer, be that a company, or a research institution actually are greatly helpful in terms of the work flow, and let the Data Scientist focus on the work rather then searching for a question to research.



### Data Dictionary

| *Column Name* | *Description* |
| :----------- | :----------- |
| state | Name of State |
| county_name | Name of County |
| unemployment_rate_2010 | 2010 Unemployment Rate |
| urban_population_prc | Urban Population % |
| rural_population_prc | Rural Population % |
| crime_per_capita | Crime Per Capita |
| per_capita_sme_num | Small and medium enterprises per capita |
| per_capita_large_num | Large enterprises per capita |
| avg_ann_pay_per_emp_sme | Average annual pay per small/medium size employer |
| avg_ann_pay_per_emp_large | Average annual pay per large size employer |
| avg_ann_pay_per_emp_total | Average annual pay per employer |
| population_jail_prc | Percentage of populatoin in jail |
| 2008_dem_%_vote | Percentage of population that voted Democrat in 2008 |
| 2008_rep_%_vote | Percentage of population that voted Republican in 2008 |
| 2008_other_%_vote | Percentage of population that voted other in 2008 |
| smoke_percent_2010 | Percentage of population that smokes |
| popul_hs_grad_prc | Percentage of population that graduated high school |
| popul_college_grad_prc | Percentage of population that graduated college |
| popul_single_paren_prc | Percentage of population that are single parents |
| liquor_stores_per10k | Number of liquor stores per 10,000 people |
| police_per_1000 | Number of police per 1,000 people |
| WhiteNonHispanicPct2010 | Percentage of white, non-hispanic people |
| BlackNonHispanicPct2010 | Percentage of black, non-hispanic people |
| AsianNonHispanicPct2010 |  Percentage of asian, non-hispanic people |
| NativeAmericanNonHispanicPct2010 | Percentage of native american, non-hispanic people |
| HispanicPct2010 | Percentage of hispanic people |
| MultipleRacePct2010 | Percentage of multi race people |

### Proper codebook order

01 Data loading and cleaning
02 EDA
03 Preprocessing and feature engineering
04 Modeling

Actual code is located in the code subfolder of the root project directory

### Additional resources

##### Graphs
graphs derived from the codebooks and saved for use in presentation

##### Tableau
graphs and maps derived from Tableau public for use in presentation

##### Data
actual folder of the initial dataset and the datasets that are pased by codebooks to the following