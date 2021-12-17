
# Project_5
### van Possum group - Jordan Gates, Joomart Achekeev, Brian Kim

## Intro
Given a wide selection of topics to work on for the project 5, van Possum group (Joomart, Jordan and Brian) has selected the vital issue of unemployment. In an attempt to model a real life project the group members have decided to ignore the available datasets and collect raw, uneddited and uncleaned data from numerous sources. The collected data included maximum information possible on such topics as numer of police per capita, number of enterprises per capita, population breakdown per capita and other related topics. The data was collected by US county for 2010, excluding the 2008 presidential election results, that have been used to derive the democrat/republican percentage of local population.

We set a very optimistic goal before actually touching the project to determine is it possible to predict unemployment rate depending on the certain characteristics of a standalone county. 

## 01 Data loading and cleaning

Due to the fact that the data was extracted from various sources, around 4.2% of the data was so corrupted and was eveluated as impossible to use in the modelling, this data was droped. Other values have been imputed with average statewide data since the rows where they were located contained other important information that would help our models learn important dependencies.

