# Traffic Stop Victim Prediction
## Introduction

According to data from the Stanford Open Policing Project, law enforcement officers in the United States perform around 50,000 traffic stops every day. The project has collected traffic stop data from 40 different states, including the city of San Francisco in California, which is the focus of our project. Previous research has found that racial profiling and bias may play a role in who gets pulled over. Therefore, our project aims to predict the race of individuals who are stopped for traffic violations based on the reason for the stop and whether or not they receive a citation. 

## Selection of Data

Data Sources: 
San Francisco Data Set (zip file): <a href="https://stacks.stanford.edu/file/druid:yg821jf8611/yg821jf8611_ca_san_francisco_2020_04_01.csv.zip"> here </a>

Stanford Digital Repository: 
<a href="https://purl.stanford.edu/yg821jf8611"> here </a>

Due to the shear breath of data our group decided to focus on San Francisco as our location for testing and training our model. The San Francisco Police Traffic Stop data contains has 905070 entries from 2008-2014. The data set includes 21 features. Some of these features are: Date, Time, Location, Latitude, Longitude, District, Age, Race, Sex, Outcome, Warning Issued. 
As part of our data pre-processing we dropped all N/A data along with columns that were not relevant to our project this included columns such as **date, time, lat, lng, district, and 7 others**.

After our inital pre-processing, we see that we now have 8 columns. All with the name non-null count. Five of our features are of dtype bool and 3 are of dtype object.

Features by Examples:

- **subject_race**: 'asian/pacific islander', 'black','hispanic', 'white', 'other'
- **subject_sex**: 'female', 'male'
- **arrest_made**: True, False
- **citation_issued (predictor variable)**: True, False
- **warning_issued**: True, False
- **outcome (predictor variable)**: 'warning', 'citation', 'arrest'
- **search_conducted**: True, False
- **search_vehicle**: True, False

Additionally we had to encode subject_race as it was catergorical data which would not work unless encoded.  

**Target**: [subject_race]

**Predictors**: [outcome, subject_sex]

## Methods

## Results

## Discussion

## Summary
