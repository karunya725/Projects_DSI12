# Project 1: SAT & ACT Analysis

## Problem Statement
Analysing the participation rates and scores of SAT and ACT, this report seeks to identity the reasons for the fluctuation of the SAT and ACT participation within US states. Using these reasons, the aim of this report is to recommend strategies to improve participation rates in at least 1 state

## Executive Summary
### Contents:
- [2017 Data Import & Cleaning](#Data-Import-and-Cleaning)
    - An uniform dataframe was ensured by dropping rows not required and removing non-numerical characters and changing all numeric columns to either an ***integer*** or ***float*** datatype
- [2018 Data Import and Cleaning](#2018-Data-Import-and-Cleaning)
    - Data imported was cleaned following the same step undertaken for 2017 data and both 2017 and 2018 data were merged into a single dataframe for ease of comparison 
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
    - The standard deviation for each numerical variable were calculated
    - The highest and lowest states were identified in terms of participation rates and mean scores
    - States with 100% participation rates and > 50% participation rates were also identified to be analysed 
- [Data Visualization](#Visualize-the-data)
    - Histograms, boxplots and scatterplots were used to investigate the data and correlations further.
- [Descriptive and Inferential Statistics](#Descriptive-and-Inferential-Statistics)
    - The mean, median, standard deviation and skewness were calculated for each numerical variable 
        - In terms of skewness, ***2017 SAT participation*** had the greatest positive skew, followed by ***2018 SAT participation***. Both ACT participation had negative skewness with ***2018 ACT participation*** having a greater skew compared ***2017 ACT participation***
        - In terms of spread of data, standard deviation, ***2018 SAT participation*** has the greatest standard deviation, followed by ***2017 SAT participation***, followed by ***2018 ACT participation*** and ***2017 ACT participation*** having the lowest
        - The shape could not be determined. However as number of states/ data points were greater than 30, we can say that the variables will fit into a normal distributions
- [Outside Research](#Outside-Research)
     - https://reports.collegeboard.org/archive/sat-suite-program-results/2017/class-2017-results 
        

## Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT/SAT|This column contains all the states|
|participation_sat17|float|SAT|The participation % for SAT per state|
|ebrw_sat17|int|SAT|The score for Evidence-Based Reading and Writing for SAT per state|
|math_sat17|int|SAT|The score for Math for SAT per state|
|total_sat17|int|SAT|The total SAT score per state|
|participation_act17|float|ACT|The participation % for SAT per state|
|composite_act17|float|ACT|The average score for ACT per state|
|english_act17|float|ACT|The score for English for ACT per state|
|math_act17|float|ACT|The score for Math for ACT per state|
|reading_act17|float|ACT|The score for Reading for ACT per state|
|science_act17|float|ACT|The score for Science for ACT per state|

## Conclusions/ Recommendations
Carrying out further research for Florida and Colorado, we aim to recommend strategies to improve SAT participation in New Mexico. 

Florida and Colorado were chosen for further research as

   - Colorado saw a drastic increase in SAT participation from 2017 (11%) to 2018 (100%) 
   - Florida saw a decrease in participation in both SAT (83% to 56%) and ACT (73% to 66%)
    
New Mexico was chosen for strategies recommendation as

   - New Mexico is neighbours with Colorado, which recently passed legislation making the SAT a mandatory as well as a subsidized exam for college-bound students, thus increasing its SAT participation to 100% 
   - New Mexico is also next to Texas, which saw an increase in SAT participation from 62% to 66%    
      - This increasing presence of the SAT in the surrounding region around New Mexico increases the likelihood for marketing efforts to be effective.    
   - Also, New Mexico saw an increase from just 11% SAT participation in 2017 to 16% in 2018, which represents almost 50% growth in a year
      - This goes to show the growth potential of that state even without much initiatives put into place. Therefore there will be a high chance for applied efforts to be receptive

Looking at the SAT collegeboard reports, it is safe to conclude that while students from a diverse background took the SAT exams in Florida and Colorado, in New Mexico, only students from families with a good edicational background took the text. 

|Highest Level Parental Education|Florida|Colorado|New Mexico|
|---|---|---|---|
|None|8%|9%|4%|
|High School Disploma|32%|23%|21%|
|Degree and higher|49%|48%|72%|
|No Response|11%|20%|3%|

- https://reports.collegeboard.org/pdf/2018-florida-sat-suite-assessments-annual-report.pdf 
- https://reports.collegeboard.org/pdf/2018-colorado-sat-suite-assessments-annual-report.pdf 
- https://reports.collegeboard.org/pdf/2017-new-mexico-sat-suite-assessments-annual-report.pdf 

Therefore to reach out to more participants in New Mexico, the college board could target the middle households and promote the fee waiver incentive to students thus increasing the diversity of participants 

Since New Mexico is a state where students have the freedom to choose the college exam they prefer, or to skip it altogether, the colleg board could get the education department to subsidise full costs of the test and thus possibly making it mandatory for all high school students to take it.
