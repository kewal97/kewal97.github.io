---
title: "Classification of Housing Ownership Using SVM"
excerpt: "A stroke is a cerebrovascular disorder that causes damage to the normal supply of blood to the brain, according to the World Health Organization (WHO). Strokes account for approximately 11% of all deaths worldwide. The condition may lead to death or long-term disability if not treated properly. The cause of strokes can be hemorrhagic or ischemic. Both hemorrhagic and ischemic strokes can occur together. Ischemic strokes are those caused by clots in the blood vessels, while hemorrhagic strokes are those caused by ruptured blood vessels. . In general, 85 percent of strokes are classified as ischemic."
---

**ABSTRACT**
The report describes the application of Support Vector Machines (SVM) for classifying housing ownership as either "Owned" or "Rented" based on several demographic and economic variables. Our analysis uses data collected via the US Census and accessed through IPUMS USA, which is a vast repository of information on people and their housing situations. The dataset is we are using is pre-processed to group the data by individual households, and irrelevant variables are removed. and use SVM with three different kernels (linear, radial, and polynomial) to model the relationship between these variables and occupancy status. The accuracy of the models is evaluated and compared with different regularization parameter (C) values. The classification results are visualized using decision boundary plots. Our findings demonstrate the predictive power of SVM in this context, with all three SVM models achieving high accuracy in predicting occupancy status.

**INTRODUCTION**

Housing issues and possession status examination is a crucial approach to comprehend the commonplace socioeconomic situations in any particular locality. In this research, we scrutinized the fundamental task of appraising support vector models' (SVM) capacity to envision whether a housing unit is owned or rented. It depends upon various demographic and housing factors.

Our aim is to ascertain the robust indicators that exert a substantial impact on the occupant rate of housing units and elucidate how these indicators can potentially be leveraged to yield reliable forecasts. For that we build a Support Vector Machine (SVM) model to predict the ownership status of houses based on various housing-related factors. The dataset used in this report is the "Housing" dataset, which contains information on the housing characteristics of a sample of households in the United States. The SVM model is trained on a subset of the dataset and is evaluated using the remaining data. The report explores the data, performs feature selection, and tunes the model parameters to achieve optimal performance. Finally, the code defines a function to plot the decision boundary of the SVM for different pairs of features. The function takes two feature names as input, and it plots a scatter plot of the data points with the decision boundary of the SVM. The function is used to plot the decision boundary for various pairs of features. the report provides a summary of the results and discusses the potential use cases and limitations of the SVM model for predicting housing ownership.

Our study is a potential useful resource for improving understanding on ownership status and housing conditions whilst laying the groundwork for policies that tackle issues regarding housing challenges in the country.

**METHODOLOGY**

PREPROCESSING:

The methodology used for cleaning the data involved several steps. Firstly, the data was imported into a pandas dataframe using the read_csv function. The dataframe was then examined using the head and info functions to get a sense of the data structure and any missing values.

Next, duplicate values were removed by grouping the data by the SERIAL column and taking the mean of the other columns. The resulting dataframe was then cleaned by dropping unnecessary columns such as SERIAL, OWNERSHPD, PERNUM, PERWT, BIRTHYR, MARST, and EDUCD, which were not relevant for our analysis.

After cleaning the dataframe, the target variable, OWNERSHP, was separated from the input features. The dataset was then split into training and testing sets, with 80% of the data reserved for training and 20% for testing. The features were scaled using the StandardScaler to ensure that all the input variables were on the same scale.

In summary, the methodology for cleaning the data involved examining the dataframe, removing duplicates, dropping unnecessary columns, splitting the dataset into training and testing sets, and scaling the features using the StandardScaler. These steps were taken to ensure that the data was in a format suitable for analysis and that the input variables were appropriately normalized.

LINEAR KERNEL:

The code implements a Support Vector Machine (SVM) using Scikit-learn library in Python with a LINEAR kernel. It trains the SVM model on a dataset and evaluates its accuracy on a testing set. The code also tests the SVM model for different values of regularization parameter and prints the accuracy to the console. It defines a function that trains an SVM model using two features and plots the decision regions using the mlxtend library.

RADIAL KERNEL:

The code implements a Support Vector Machine (SVM) using Scikit-learn library in Python with a RADIAL kernel. It trains the SVM model on a dataset and evaluates its accuracy on a testing set. The code also tests the SVM model for different values of regularization parameter and prints the accuracy to the console. It defines a function that trains an SVM model using two features and plots the decision regions using the mlxtend library.

POLYNOMIAL KERNEL:

The code implements a Support Vector Machine (SVM) using Scikit-learn library in Python with a POLYNOMIAL kernel. It trains the SVM model on a dataset and evaluates its accuracy on a testing set. The code also tests the SVM model for different values of regularization parameter, degree values and prints the accuracy to the console. It defines a function that trains an SVM model using two features and plots the decision regions using the mlxtend library.

**COMPUTATIONAL RESULTS**

LINEAR KERNEL:

<img width="322" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/88125e1e-d3ef-4447-b00e-cc4bb1bd1bd7">

C = 0.1 gives best accuracy for my model with value of 0.84694043.

<img width="312" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/4c10d030-b522-474e-8131-42851fd12365">

From the confusion matrix, 4031 values of OWNERS and 1187 values of RENTERS are classified correctly. 644 values of RENTERS are misclassified as RENTERS and 299 OWNERS are misclassified as RENTERS.

RADIAL KERNAL:

<img width="335" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/6fb7b7c5-6026-44be-abba-29d3bbb113de">

C = 1 gives the best accuracy.

<img width="340" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/01848923-5dc4-4810-9bcd-6c85fa81a47c">

From the confusion matrix, 4102 OWNERS and 1186 RENTERS are correctly classified. 645 RENTERS are misclassified as OWNERS. 228 OWNERS are misclassified as RENTERS.

POLYNOMIAL KERNEL:

<img width="468" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/314ebc34-e583-4a58-84d8-fea1c5b6125e">

C = 0.1, gamma = 1 and degree = 3 gives best accuracy.


<img width="338" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/50a708cf-3b07-4f49-8cd0-309af0d5f0ff">

4087 OWNERS and 1139 RENTERS are correctly classified. 692 RENTERS are classified as OWNERS and 243 OWNERS as RENTERS.

**DISCUSSION**

For Linear Kernel:

<img width="360" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/97283b49-bb66-42c5-a901-7119cdcd3b7b">

Out of the several decision boundary plots I have made for leaner kernel I will discuss the two strong predictor variables I found, The decision boundary plot shows separation of the two classes in the dataset based on the values of the two selected features ('ROOMS' and 'HHINCOME'). The plot shows the decision boundary as a straight line (linear boundary) that separates the data points into two regions, one for each class The legend indicates that the blue color represents the 'Owned' class, while the orange color represents the 'Rented' class. The plot also shows the support vectors as filled circles, and the data points that lie on the wrong side of the decision boundary as crossed circles, we can see there are many misclassified points on both the side of margin. But still the corelated accuracy between these two variables came out to be around 80%.

For Radial Kernel:

<img width="384" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/016c8c2d-cc84-435f-bd30-d78fa80cf14e">

Out of the several decision boundary plots I have made for Radial kernel I will discuss the two strong predictor variables I found, The decision boundary plot shows the classification of two categories of 'Owned' and 'Rented' based on the two input features 'ROOMS' and 'AGE'. The SVM model used a radial basis function (RBF) kernel with a regularization parameter C = 0.1 to learn the decision boundary.

The shaded regions represent the predicted class for different combinations of the two input features. The decision boundary is a non-linear curve since we used the RBF kernel. The support vectors, which are the closest data points to the decision boundary, are shown as circled points. The legend shows the two classes and their corresponding colors.

The accuracy of the model on the test set for the given combination of input features is printed to the console. In this case, the accuracy is 0.8076610939782503, which means that the model correctly classified 80.77% of the test samples.

For Polynomial Kernel:

<img width="388" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/9ade692b-f77a-463f-b9d0-b24e43960f61">

Out of the several decision boundary plots I have made for Radial kernel I will discuss the two strong predictor variables I found, This The decision boundary plot for the SVM model with polynomial kernel shows the separation of the two classes, 'Owned' and 'Rented', based on the features 'AGE' and 'ROOMS'. The shaded regions indicate the predicted class for the corresponding feature values. The colored points represent the training data points with their respective class labels, and the black points represent the support vectors.

The polynomial kernel with a degree of 3 was used in this model, which means the decision boundary is a third-degree polynomial curve that separates the two classes. The accuracy of the model on the test set is 0.7778, which means the model correctly predicted the class for 77.78% of the test set samples. We also see many misclassified points on both side of the region, The plot shows that the model could not capture the underlying patterns in the data very well, which could be due to the complex interaction between the features that cannot be captured by a simple polynomial curve.


I have also made some plots to help describe few relationships in better way 

<img width="368" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/11dacd2c-b9cf-4bf7-b4c5-77c968d68a06">

This plot shows the average income by the number of vehicles owned by households. The x-axis represents the number of vehicles, and the y-axis represents the average income of households that own that number of vehicles. The bar graph shows that as the number of vehicles owned by households increases, the average income also tends to increase. This graph can be useful in identifying income patterns and understanding the relationship between income and vehicle ownership.

<img width="356" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/5e8999a7-9edf-4077-a70c-e41e2d007965">

The second plot shows the average number of family members by the number of rooms in households. The x-axis represents the number of rooms, and the y-axis represents the average number of family members in households with that number of rooms. The line graph shows that as the number of rooms in households increases, the average number of family members tends to increase as well, although the relationship appears to level off at around 5-6 rooms. This graph can be useful in understanding household size patterns and in determining appropriate housing size for different family sizes.


**CONCLUSION**

In conclusion, we have applied Support Vector Machines (SVMs) with three different kernels: linear, radial, and polynomial to predict homeownership status based on a dataset containing various socio-economic variables. We preprocessed the data by removing duplicates, dropping unnecessary columns, splitting the dataset into training and testing sets, and scaling the features using the StandardScaler.

Our results show that the radial kernel with a regularization parameter C = 1 performs the best among the three kernels, correctly classifying 85.83% of test samples, followed by the polynomial with C = 0.1, gamma = 1, and degree = 3 gives an accuracy of 84.82% and then linear kernel with a regularization parameter C = 0.1 and an accuracy of 84.69%.

Our decision boundary plots reveal that the two strongest predictor variables for the linear kernel are 'ROOMS' and 'HHINCOME', while for the radial kernel, they are 'ROOMS' and 'AGE'. For the polynomial kernel, we found that the strongest predictor variables are 'HHINCOME' and 'AGE'. From the findings, the households with moderate number of ROOMS has more positive ownership and the ownership increases with increase in AGE and its maybe because people tends to settle by having their own house after certain ages.

In summary, our study provides insights into the effectiveness of SVMs with different kernels in predicting homeownership status. The results suggest that SVMs can be a useful tool for analyzing complex socio-economic data and predicting homeownership status with reasonable accuracy.

**BIBLIOGRAPHY**

1. Ruggles, S., Flood, S., Sobek, M., Brockman, D., Cooper, G., Richards, S., & Schouweiler, M. (2023). IPUMS USA: Version 13.0 [Dataset]. Minneapolis, MN: IPUMS. https://doi.org/10.18128/D010.V13.0.

2. Cortes, C. & Vapnik, V. (1995). Support-vector networks. Machine Learning, 20(3), 273-297.
