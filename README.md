# Traffic Stop Victim Prediction
## Introduction

According to data from the Stanford Open Policing Project, law enforcement officers in the United States perform around 50,000 traffic stops every day. The project has collected traffic stop data from 40 different states, including the city of San Francisco,  CA, which is the focus of our project. 

Previous research has found that racial profiling and bias may play a role in who gets pulled over. Our project aims to predict the race of individuals who were stopped for traffic violations based on the reason for the stop and whether or not they receive a citation.

## Selection of Data

Data Sources: 
San Francisco Data Set (zip file): <a href="https://stacks.stanford.edu/file/druid:yg821jf8611/yg821jf8611_ca_san_francisco_2020_04_01.csv.zip"> here </a>

Stanford Digital Repository: 
<a href="https://purl.stanford.edu/yg821jf8611"> here </a>

Due to the breath of data provided in the Stanford Open Policing Project, our group decided to focus on San Francisco as the location for testing and training our model. The San Francisco Police Traffic Stop data contains 905,070 entries from 2008 to 2014 and includes 21 features. As part of our data pre-processing, we dropped all entries containing N/A values along with columns that were not relevant to our project.

After pre-processing, we have 8 columns. Five of our features are booleans and 3 are an object data type.

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
**Toos**:
- Numpy, Pandas, Matplotlib, and Seaborn for data analysis and visualization
- Scikit-learn for inference
**Inference Methods used with Scikit**:
- Models: kNN Classification, Forward Selection, Decision Tree Classification, Non-Linear SVC Classification
- Features: StandardScaler, LabelEncoder

## Results

## Discussion

## Summary

## References
Stanford Open Policing Project et al. (2020-04-03) U.S. Police Traffic Stop Data by City & State 2020 v4. Stanford Digital Repository. Available at: http://purl.stanford.edu/yg821jf8611
