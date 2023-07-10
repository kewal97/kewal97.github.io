---
title: "A Decision Tree Analysis on Drug Use and Health"
excerpt: "This report contains the analysis of factors that are associated with youth drug use, using decision tree 
models on survey data from the National Survey on Drug Use and Health. The dataset contains detailed information 
on various aspects of respondents' lives, including demographics, youth experiences, and substantial drug use. 
The study explores three problem types: binary classification for marijuana use, multi-class classification for 
frequency of marijuana in past year, and regression for first ever use of marijuana. Decision trees and some ensemble
methods are used to build predictive models for each problem type. The results suggest the impact of different 
demographic variables and youth experience variables on various substantial youth drug uses. The findings of this 
study have practical implications for public health interventions aimed at reducing youth drug use."
---
**ABSTRACT**
This report contains the analysis of factors that are associated with youth drug use, using decision tree 
models on survey data from the National Survey on Drug Use and Health. The dataset contains detailed information 
on various aspects of respondents' lives, including demographics, youth experiences, and substantial drug use. 
The study explores three problem types: binary classification for marijuana use, multi-class classification for 
frequency of marijuana in past year, and regression for first ever use of marijuana. Decision trees and some ensemble
methods are used to build predictive models for each problem type. The results suggest the impact of different 
demographic variables and youth experience variables on various substantial youth drug uses. The findings of this 
study have practical implications for public health interventions aimed at reducing youth drug use.

**INTRODUCTION**
Our research aims to predict the determinants of youth drug use using decision trees and ensemble methods drawn from 
the National Survey on Drug Use and Health. The survey is demographically representative of non-institutionalized 
populations in the US; it offers a wealth of information regarding drug use patterns alongside pertinent details like
age, gender, race/ethnicity mental health conditions. For close to five decades, SAMHSA has sponsored this annual 
study that features an aggregated dataset composed of approximately 300 variables cataloging around 70K respondents 
aged twelve or more. 

The study at hand will concentrate on three variables associated with marijuana use, namely 'mrjflag' which denotes 
the respondent's history of using marijuana; 'mrjydays,' indicating the number of days that the respondent used 
marijuana in the previous year, and 'irmjage' signifying the first age when they indulged in cannabis usage. 
The goal is to employ decision trees to predict whether an individual has ever consumed marijuana (binary classification), 
how many days they indulged in cannabis use during the last year (multi-class classification), and ultimately assess 
their initial age for consuming marijuana (regression). 

Our analytical approach will encompass more than just decision trees. We are planning to employ ensemble methods 
such as random forests and boosting to increase our models' accuracy. In this study, we intend to use decision trees
and ensemble methods to analyze the dataset comprehensively, It is our aim to identify factors associated with youth
drug use and provide insights that can be used to inform public health policies that aim to reduce teen drug use.

**METHODOLOGY**
Data Cleaning:
The dataset was filtered during the data cleaning process to remove observations with invalid or missing values. To be more specific, the dataset was filtered using the following criteria:
1.The values of 98 or 99 in the variable EDUSCHGRD2 were removed from the dataset.
2.The values of 94, 97, 98, or 99 in the variable eduskpcom were removed.
3.The observations with values of 3 or 4 in the variables imother and ifather were removed.
4.The observations with a value of 3 in the variable PDEN10 were removed.
5.Finally, any observations with missing values in the columns related to youth experience were removed.

Upon completion of the data cleaning process, the dataset underwent further analysis to identify three subsets 
categorized for different analysis techniques- binary classification, multiclass classification, and regression 
analysis. These segregated data sets were further used to create decision trees and ensemble models utilizing the 
relevant classification or regression approach.

Binary classification:
In the binary classification, the "mrjflag" that is marijuana ever used (0=never, 1=ever) column is used as the 
response variable, while only the data from demographic and youth experience columns are used as predictor variables.
The data is split into training and testing sets, and a decision tree is created using the "tree" function. Later using
the testing data and the "predict" function the accuracy of the tree model is evaluated. I tried to then pruned the 
decision tree using cross-validation with the "cv.tree" function used best = 3 and eventually got exactly the same 
result as a normal decision tree with same accuracy after that used  the the "importance" function to compute 
the important variable.

Multiclass classification:
In the multi-class classification, the "mrjydays" that is the number of days of marijuana in past year column is used 
as the response variable, which is converted to a factor variable. The same predictor variables are used as in the 
binary classification (demographic and youth experience). The data is split into training and testing sets again, 
and a decision tree is created using the "tree" function. The variable importance is computed using the "importance" 
function. and finally, The accuracy of the tree model is evaluated using the testing data and the "predict" function. 
The variable importance is computed using the "importance" function.

Regression:
In the regression classification, the "irmjage" marijuana age of first use column is the targeted variable, while only
the data from demographic and youth experience columns are used as predictor variables same as binary and multi-class
classifications. Data is cleaned where we used an observation 991 where marijuana is never used also checked for if 
there are any missing values. The data is split into training and testing sets, and a decision tree is created using 
the "tree" function. I tried to perform pruning but ended up getting the same result as normal decision tree so, 
three regression methods used are decision tree, bagging and random forest. The mean squared error is calculated for 
each method for the comparison of models. the "varImpPlot" function is used to plot the variable importance.

**COMPUTATIONAL RESULTS**
1. BINARY CLASSIFICATION

Accuracy values of different models used for binary classification are as follows: 
•	Decision Tree - 0.8811777
•	Prune – 0.8811777
•	Bagging – 0.8895899
•	Random Forest – 0.8885384

According to the accuracy of the models, the best model to predict if marijuana is ever used or not is bagging with 
an accuracy of 0.8895899.

2. MULTI-CLASS CLASSIFICATION

Accuracy values of different models used for multi-class classification are as follows: 
•	Decision Tree – 0.8790747
•	Prune – 0.8790747
•	Bagging – 0.873817
•	Random Forest – 0.8706625

According to the accuracy of the models, the best model to predict number of days marijuana was used in past year
are Decision tree & prune as both of them are giving same accuracy of 0.8790747.

3. REGRESSION

MSE values of different models used for multi-class classification are as follows: 
•	Decision Tree – 2.076836
•	Prune – 1.702468
•	Bagging – 1.831604
•	Random Forest – 1.616788

According to the MSE of the models, the best model to predict age that marijuana was used for the first time is 
random forest giving the least MSE of 1.616788.

**DISCUSSION**
1. BINARY CLASSIFICATION
<img width="500" alt="Screenshot 2023-07-10 at 2 03 14 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/702cf5b6-a793-4032-a5c8-619bbbc55c6b">

<img width="520" alt="Screenshot 2023-07-10 at 3 34 06 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/35ec3c4a-f30b-45a8-80c5-9b069a3169b2">

The first question being asked at the root node is whether the respondent approves or disapproves of marijuana use. If they strongly or somewhat disapprove, the algorithm moves down the left branch, and if they neither approve nor disapprove, it moves down the right branch.

At its left node, the algorithm is asking whether any of the students in the respondent's grade take marijuana. If most or all of them do not take marijuana, it moves down to it’s left branch, and if most or all of them do take marijuana, it moves down to its right branch.

At its left node, the algorithm is asking how their close friends feel about youth taking marijuana. If they strongly or somewhat disapprove of taking marijuana, then the youth are more likely to never used marijuana. 

BAGGING:

BAGGING is my best model according to the accuracies.
<img width="401" alt="Screenshot 2023-07-10 at 3 37 56 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/4362bfbd-215e-46ba-ba0d-dacfcc145c95">

According to the confusion matrix, 782 of youth who never used marijuana are classified correctly and 64 youth who uses marijuana are predicted correctly.
77 people who uses marijuana are misclassified as never used and 28 people that doesn’t use marijuana are misclassified as used.
<img width="585" alt="Screenshot 2023-07-10 at 3 48 55 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/5d04e968-f762-4ece-a743-8cb723be955d">
According to the plot, the most important variables that can predict if a person ever used marijuana or not are yflmjmo (how yth feels: peers using marijuana monthly), FRDMEVR2(rc-yth think: close frnds feel abt yth try marijuana), stndsmj(number of students in yth grade use marijuana), frdmjmon(rc-yth think: clse frnds feel abt yth use marijuana mon), YFLTMRJ2(rc-how yth feels: peers try marijuana).

2. MULTI – CLASS CLASSIFICATION:

Example decision tree:
![image](https://github.com/kewal97/kewal97.github.io/assets/116126736/d12bf653-64f5-490e-9ade-6c5d4e9b70e4)
According to the accuracy of the models, the best model to predict number of days marijuana was used in past year are Decision tree & pruning.

![image](https://github.com/kewal97/kewal97.github.io/assets/116126736/03461b76-5e52-4ceb-98df-7931b8912aa8)
The confusion matrix shows the number of predicted values that match or do not match the actual values in the test dataset for a multi-class classification problem. The rows of the matrix represent the predicted values, and the columns represent the actual values. In this ![image]











