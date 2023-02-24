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
**Toos**:
- Numpy, Pandas, Matplotlib, and Seaborn for data analysis and visualization
- Scikit-learn for inference
**Inference Methods used with Scikit**:
- Models: kNN Classification, Forward Selection, Decision Tree Classification, Non-Linear SVC Classification
- Features: StandardScaler, LabelEncoder

**San Francisco Data Set (zip file)**: https://stacks.stanford.edu/file/druid:yg821jf8611/yg821jf8611_ca_san_francisco_2020_04_01.csv.zip

**Stanford Digital Repository**: https://purl.stanford.edu/yg821jf8611

The San Francisco Police Traffic Stop data contains has 905070 entries from 2008-2014. The data set includes 21 features. Some of these features are: Date, Time, Location, Latitude, Longitude, District, Age, Race, Sex, Outcome, Warning Issued. For the purpose of our objective, we have decided to drop variables that were not relevant to our project.

**Target**:
- race

**Predictors**:
- outcome
- subject_sex

## Results
![citation_warning__female_male](https://user-images.githubusercontent.com/40731237/221099540-6c8980ba-3035-472f-9f2d-cb344887f6e6.png)

First we will explore two differnt variables in from the datase. On the left plot, we conducted a bar plot that displays the amount of citations vs warnings that were given. We see that police officers in this dataset gave more citations than warnings.

Next, we see that police officers performed traffic stops on male subjects more than females.

![search_arrest_by_race](https://user-images.githubusercontent.com/40731237/221099533-b9311498-352b-4188-87e2-3a065988dad0.png)

The plot on the left gives us some context to outcome of getting your vehicle searched based on race. We see that police officers performed more vehicle searches on Black individuals when compared to other subjects.

The plot on the right gives context to the outcome of the traffic stop based on race. We see cases of police officers arresting Black individuals more than other subjects.

![age](https://user-images.githubusercontent.com/40731237/221099522-ad625b2c-0226-4401-a145-b7fc324361f0.png)

Lastly, we see that our dataset has a high density of subjects ranging from 20-30 years old.

When we use a violinplot to see age distribution by race.
## Discussion

## Summary

## References
Stanford Open Policing Project et al. (2020-04-03) U.S. Police Traffic Stop Data by City & State 2020 v4. Stanford Digital Repository. Available at: http://purl.stanford.edu/yg821jf8611
