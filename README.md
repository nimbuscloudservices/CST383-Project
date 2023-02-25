# Traffic Stop Victim Prediction
Project Video Presentation: <a href="https://youtu.be/t6lJ6b_S-RQ">here</a>
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
- **citation_issued**: True, False
- **warning_issued**: True, False
- **outcome**: 'warning', 'citation', 'arrest'
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

**Traffic Data**

![citation_warnings_sex_searched](https://user-images.githubusercontent.com/40731237/221310248-1fd5d76c-3b19-4c42-933a-387f74ac0cdb.png)

First we will explore variables from the data. On the left plot, we have the amount of citations vs warnings given. On the middle plot, we have traffic stops by sex of the individual stopped. And on the right plot, we see that if a search is made, an arrest is likely.

**Traffic Data by Race**

![search_arrest_by_race](https://user-images.githubusercontent.com/40731237/221310409-0820452a-4cc6-4010-b422-630de70d7cdd.png)

Police officers performed more vehicle searches on Black individuals when compared to other races.

Police officers are arresting White individuals more than other races.

**Distribution by Race**

![dist_race](https://user-images.githubusercontent.com/40731237/221343744-aefee3ef-2408-4847-8050-4628957b1001.png)

There are more white subjects in the dataset.

**Traffic Data by Age**

![age](https://user-images.githubusercontent.com/40731237/221310652-513d2bc7-327f-4d27-a963-3132eb7216ea.png)

The dataset has a high density of subjects ranging from 20-30 years old. We used a violin plot to represent the age of people stopped, distributed by race.

## Discussion
During our project, we encountered some challenges with accuracy, as our initial results were largely under 40% when trying to predict between all races. However, we were able to increase our accuracy to 60% by simplifying the models to predict between White and not White victims.

Despite this improvement, we noticed that our models tended to overfit the data. One possible explanation for this is that we had to use a small sample size in order to run the models on Collaboratory. To produce conclusive results, we believe it would be beneficial to leverage a better platform for running these models.

Additionally, our findings did not coincide with other research that suggests Black drivers are more likely to be pulled over. We used three different classification algorithms - KNN, Non-Linear SVC, and Decision Tree - but found that they were not fast enough to process all of the data before Collaboratory would time out. In future iterations of this project, we would consider using other algorithms such as Random Forest or Xgboost to improve processing times.

## Summary
For this project we used three different models: KNN, Decision Tree, and SVC. There was a total of 5 observations. In the first three observations we used all races in the dataset ('asian/pacific islander', 'black','hispanic', 'white', 'other'). We noticed a low accuracy scores for these models. There was a slight improvement in accuracy score when we used the Decision Tree and SVC models but overall scores remained below 50%. 

Based on the distribution of race on the dataset, we wanted to see how the models would predict if the subject was White or another race. This led us to conduct 3 additional observations. To do this we combined all the other races that are not Black and performed the same three models. Our accuracy scores improved from tuning our data and obtained scores higher than 50%. The Decision Tree model gave us the best accuracy score. 

Apart from our models we also examined the effect of features. We noticed that increasing the number of predictor features did not improve our accuracy score.We also saw how increasing the training set size did not improve our test accuracy score. In addition, we saw cases of both overfitting and underfitting in our learning curves. 

Our project's objective was to see if we can predict the subject's race based on two features, outcome and subject age. Based on our models, our results show that there is a better chance of predicting if the subject is either Black or another race. 


## References
Stanford Open Policing Project et al. (2020-04-03) U.S. Police Traffic Stop Data by City & State 2020 v4. Stanford Digital Repository. Available at: http://purl.stanford.edu/yg821jf8611
