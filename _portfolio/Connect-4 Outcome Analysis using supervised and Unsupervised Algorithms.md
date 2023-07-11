---
title: "Connect-4 Outcome Analysis using supervised and Unsupervised Algorithms"
excerpt: "This project aims to investigate various supervised and unsupervised algorithms for analyzing the Connect-4 game dataset. The dataset consists of legal game positions in Connect-4 where neither player has achieved victory yet, and the next move is not predetermined. The project commences with data visualization, including a bar plot representing the distribution of outcomes and a heatmap illustrating the game board positions. To pre-process the data, categorical features are encoded using one-hot encoding. Several supervised algorithms such as Logistic Regression, Decision Trees, Support Vector Machines, and Neural Networks are employed, alongside unsupervised learning techniques like K-means clustering. The performance of the supervised learning algorithms is evaluated based on accuracy, while the unsupervised clustering approach is evaluated using metrics such as the silhouette score and completeness score. This project aims to provide valuable insights into the efficacy of different techniques for analyzing the Connect-4 dataset."
---

**ABSTRACT**

This project aims to investigate various supervised and unsupervised algorithms for analyzing the Connect-4 game dataset. The dataset consists of legal game positions in Connect-4 where neither player has achieved victory yet, and the next move is not predetermined. The project commences with data visualization, including a bar plot representing the distribution of outcomes and a heatmap illustrating the game board positions. To pre-process the data, categorical features are encoded using one-hot encoding. Several supervised algorithms such as Logistic Regression, Decision Trees, Support Vector Machines, and Neural Networks are employed, alongside unsupervised learning techniques like K-means clustering. The performance of the supervised learning algorithms is evaluated based on accuracy, while the unsupervised clustering approach is evaluated using metrics such as the silhouette score and completeness score. This project aims to provide valuable insights into the efficacy of different techniques for analyzing the Connect-4 dataset.

**INTRODUCTION**

This project aims to explore and analyze the Connect-4 game dataset using a variety of supervised and unsupervised algorithms. Connect-4 is a popular two-player board game where the objective is to connect four discs of the same color in a row, column, or diagonal on a grid. The dataset used in this project comprises legal game positions in Connect-4, where neither player has achieved victory yet and the next move is not predetermined.

Goals:

The primary goal of this project is to examine the effectiveness of different techniques for analyzing the Connect-4 dataset. The project will employ both supervised learning algorithms, such as Logistic Regression, Decision Trees, Support Vector Machines, and Neural Networks, as well as unsupervised learning techniques, specifically K-means clustering.

Dataset Description:

The dataset utilized in this project contains legal game positions in the Connect-4 game, focusing on situations where neither player has achieved victory yet and the next move is not forced. Each instance in the dataset represents a unique game state, characterized by various features such as the positions of the players' discs on the game board. The dataset provides the necessary information to explore strategies, patterns, and potential winning moves in Connect- 4.
By employing a range of supervised and unsupervised algorithms, along with comprehensive data visualization techniques, this project seeks to uncover valuable insights into the Connect- 4 dataset and shed light on the effectiveness of different analytical approaches.

**METHODOLOGY**
The initial step in the methodology involves importing the necessary libraries and loading the Connect-4 dataset, which contains legal positions in the game of Connect-4. The dataset is read into a Pandas Data Frame, and appropriate column names are assigned to the dataset's columns. To ensure data quality, a check is performed to identify any missing values, and it is determined that the dataset does not contain any null values. Visualizations, such as bar plots and heatmaps, are created to gain insights into the distribution of the outcome variable (win, loss, or draw) and the positions on the Connect-4 board. Then the dataset is divided into two components: the features(X) and the target variable(y). The features represent the positions on the Connect-4 board, denoted as black, player 1(x), or player 2(o). The target variable indicates the class of the game outcome. To facilitate analysis, one-hot encoding is applied to categorical features. The class labels are mapped to numerical values. Finally, the dataset is split into training and testing sets using the train-test split technique, which will be utilized in subsequent steps of the methodology.

Logistic Regression:

Logistic regression is performed using the Logistic Regression class from scikit-learn, and the accuracy of the model is calculated.

Decision Trees:

Next, a decision tree classifier is fitted to the data. The accuracy of the decision tree on the test data is calculated, and feature importance’s are determined. The feature importance’s indicate the relative importance of each feature in predicting the outcome.\

Random Forest:

Random forest, an ensemble learning method, is employed in this step. The random forest classifier is trained on the training data, and predictions are made on the test data. The accuracy of the model is calculated, and the feature importance’s are determined. The top five important features are visualized using a bar plot.

Boosting:

In this step, gradient boosting is utilized. A gradient boosting classifier is created and fitted to the training data. Predictions are made on the test data, and the accuracy of the model is calculated. Feature importance’s are determined, indicating the most important features in the dataset.

Support Vector Machines (SVM):

Two types of SVMs are employed in this step: linear SVM and radial SVM. Feature selection is performed using SelectKBest with an F-score. The selected features are used to train the SVM models. Predictions are made on the test data, and the accuracies of both linear SVM and radial SVM are calculated.

Neural Networks:

The model architecture is defined using the Sequential model from TensorFlow. The model consists of three dense layers. The first dense layer has 64 units and uses the ReLU activation function. It accepts input with a shape corresponding to the number of features in the training data. The second dense layer has 32 units and also uses the ReLU activation function. The final dense layer has a number of units equal to the number of classes, and it employs the softmax activation function to produce class probabilities. After defining the model architecture, it is compiled using the Adam optimizer, categorical cross-entropy loss function, and accuracy as the evaluation metric. This step involves training a neural network model using the Keras library. The target variable is converted to categorical format, and the model architecture is defined. The model is trained on the training data and evaluated on the test data. The accuracy of the neural network model is calculated.

SVD:

SVD is then performed on the encoded data to decompose it into U, s, and Vt matrices, representing the singular vectors and singular values. The proportion of variance explained by each principal component is calculated, and a scree plot is generated to visualize the variance explained by each component.
In the next step, the data is projected onto the first two principal components, creating a lower- dimensional representation. This is done by multiplying the centered encoded data with the first two columns of the Vt matrix. The resulting matrix, X_pca, represents the data projected onto the first two principal components. A scatter plot is then created, where the x-axis

Clustering:

In the methodology, the K-means clustering algorithm is employed to group the data into distinct clusters. The algorithm is applied to the encoded data, with a specified number of clusters (in this case, 3). The resulting cluster labels are then assigned to the original data. The observations within each cluster are displayed to examine the characteristics of the data points belonging to the same cluster.
To evaluate the clustering results, a scatter plot is created using the first two principal components obtained from the dimensionality reduction step. The data points are colored based on their assigned cluster labels, providing a visual representation of the clustering outcomes. Additionally, two performance metrics are computed. The completeness score is calculated to measure the extent to which each true class is assigned to a single cluster. The silhouette score is used to evaluate the compactness and separation of the clusters, indicating the quality of the clustering results.
In summary, the methodology encompasses data processing, application of various machine learning algorithms such as logistic regression, decision trees, random forest, gradient boosting, SVMs, neural networks and clustering. It also includes feature selection, accuracy evaluation, and visualization of feature importances. These steps provide insights into the performance and predictive capabilities of different machine learning models for the Connect- 4 dataset.

**COMPUTATIONAL RESULTS**

<img width="595" alt="Screenshot 2023-07-10 at 11 44 04 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/a53d0270-3dcc-4d77-bef4-8bddb5faee7f">

The table provides insights into the performance of different models and the clustering algorithm on the given dataset. The accuracy metric represents the percentage of correctly classified samples, while the silhouette score and completeness score measures how well the clusters capture the original classes. Based on the results, the random forest model achieved the highest accuracy, indicating its effectiveness in predicting the target variable. The linear SVM and clustering algorithm performed relatively poorly compared to other models, suggesting that the dataset may not exhibit clear linear separability or distinct clustering patterns.

**DISCUSSION**

<img width="463" alt="Screenshot 2023-07-10 at 11 45 56 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/8fe2a9e7-dc1f-41e4-84fb-645973953895">

The given figure illustrates the Outcome Distribution for the connect-4 dataset, revealing an imbalance in the data distribution. However, it is noteworthy that an ample number of data points are available for each outcome category. Consequently, we can confidently proceed with this project.

<img width="510" alt="Screenshot 2023-07-10 at 11 47 03 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/6159c446-50e5-403c-baa4-946a4ddfe597">

The provided visualization depicts the Connect-4 game board positions. In this representation, the number 0 corresponds to the empty spaces on the board. Player 1's positions are represented by a lighter shade of blue, indicated by the number 1. Similarly, player 2's positions are denoted by a darker shade of blue, represented by the number 2. This visualization offers a clear overview of the distribution and placement of the players' moves on the Connect-4 game board.

Random Forest Results:

Random Forest is the best model according to the accuracy values.

<img width="324" alt="Screenshot 2023-07-10 at 11 47 56 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/3c9844cb-0ec7-4f65-b99a-e072b51af649">

The plot displays the top 5 feature importances obtained from the random forest model. The x- axis represents the feature names, while the y-axis represents the importance scores assigned to each feature. The heights of the bars in the plot indicate the relative importance of the corresponding features. The higher the bar, the more significant the feature is in predicting the target variable. These features have been ranked based on their contribution to the model's predictive performance.
Analyzing feature importances is essential for understanding the underlying factors that drive the model's predictions. It helps identify which features have the most influence on the target variable and can aid in feature selection or feature engineering processes.

<img width="325" alt="Screenshot 2023-07-10 at 11 48 58 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/920e57e2-2311-4668-8427-a1f2dd196601">

The confusion matrix plot provides an overview of the performance of the random forest model by visually representing the predicted and actual values of the target variable, The diagonal elements of the confusion matrix represent the instances that were correctly classified, while the off-diagonal elements represent the instances that were misclassified.

<img width="393" alt="Screenshot 2023-07-10 at 11 49 40 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/b6c40e6e-6d1f-4fbb-b538-39180fc0bc08">
<img width="390" alt="Screenshot 2023-07-10 at 11 50 29 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/a087aa01-c40d-4213-bf96-7e7361aca9d6">

The above plots represent countplot for the top 5 important variables based on the feature importances obtained from the random forest model. Each countplot visualizes the distribution of values for a specific variable, grouped by the outcome variable. In each countplot, the x-axis
represents the values of the selected variable, and the y-axis represents the count of occurrences. The countplot is further differentiated by color, with each color representing a different outcome category.
By examining these countplots, we can gain insights into the relationship between the top variables and the outcome variable. We can observe the distribution of values for each variable across different outcome categories. This allows us to explore potential associations and gain a better understanding of how these variables contribute to the prediction of the outcome.
The count plots suggest that if player 1 marks positions 6 and 12 on the game board, their chances of winning are higher. Additionally, if positions 0, 18, and 36 are empty (blank spaces), it increases the likelihood of player 1 winning.

Neural Network Performance Visualization:

<img width="298" alt="Screenshot 2023-07-10 at 11 51 20 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/5936b672-3652-4fe4-b986-d622ad60480e">

The neural network model that was trained achieved an impressive test accuracy of 79.55%. There is potential for further improvement by either developing a more robust model or making modifications to the existing model. Exploring different neural network architectures in future endeavours could lead to more advanced analyses and insights for the Connect-4 game.

Singular Value Decomposition (SVD):

<img width="444" alt="Screenshot 2023-07-10 at 11 52 18 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/7fbed6c8-adda-4b18-909b-d0d37ceb637a">

The scree plot is a graphical representation of the eigenvalues of the principal components, showing the amount of variance explained by each component.
If you observe that the scree plot has a clear elbow or cutoff point, where the eigenvalues sharply drop after a certain number of components, it suggests that only a few principal components contribute significantly to the variance explained. In this case, it appears that the first eight principal components contribute to a larger proportion of the total variance, while the remaining components have minimal effect on the variance.
This finding can be useful for dimensionality reduction purposes. Instead of using all the components, you may consider retaining only the first eight components that explain the majority of the variance. By doing so, you can reduce the dimensionality of your data while still preserving most of the relevant information.

# Discuss the interpretation of the U and V* matrices
The U matrix from SVD represents the left singular vectors and can be interpreted as the transformed feature matrix. Each row of U corresponds to a data point, and each column
represents a linear combination of the original features that capture the underlying patterns in the data.
The V* matrix from SVD represents the right singular vectors and can be interpreted as the transformed variable matrix. Each row of V* represents a principal component, and each column corresponds to a feature in the original dataset. The entries in V* represent the weight or importance of each feature in the corresponding principal component.

<img width="452" alt="Screenshot 2023-07-10 at 11 53 00 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/2fc0e6c7-871c-4587-8a33-744850f44205">

Discuss the structure within the data and the difference from plotting on the original features The plot of the data in the first two principal components shows the inherent structure or patterns in the data. Points that are close to each other in the plot are more similar in terms of their underlying patterns. This structure captures the relationships between the original features in a reduced-dimensional space.
Compared to plotting on the two original features, the plot in the principal components provides a more condensed representation of the data, as it combines multiple original features into the principal components. This can help in identifying clusters or groups of similar data points more easily.

Clustering:

<img width="452" alt="Screenshot 2023-07-10 at 11 53 00 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/f82ec42d-9013-4653-81b8-b4f39ad1b9cc">

Overall, the low values for both the clustering completeness score and clustering silhouette score imply that the clustering algorithm used in this context is not performing well in accurately capturing the true class assignments and creating distinct, well-defined clusters for the Connect-4 dataset.
The low values of the clustering completeness score and clustering silhouette score suggest that there may not be clear and discernible patterns in the data that can be effectively captured by the clustering algorithm. In such cases, it becomes challenging for the algorithm to identify meaningful clusters that correspond to the underlying structure or class assignments in the data. The absence of distinct patterns or structures may hinder the performance of the clustering algorithm, resulting in low scores. It could indicate that the Connect-4 dataset does not exhibit easily separable clusters or that other factors, such as noise or overlapping data points, are present, making it difficult for the algorithm to accurately cluster the data.

**CONCLUSION**

In conclusion, this report presented a comprehensive methodology for analyzing the Connect- 4 dataset using various machine learning techniques. The dataset was pre-processed and cleaned, ensuring data quality and appropriate formatting for analysis. Several models were applied, including logistic regression, decision trees, random forest, boosting, SVMs, and neural networks, to predict the outcome of the Connect-4 game. Additionally, a clustering algorithm (K-means) was used to group similar samples together based on their features.
The computational results demonstrated the performance of each model and the clustering algorithm. The random forest model achieved the highest accuracy of 81.94%, indicating its effectiveness in predicting the outcome. The neural network model also performed well with an accuracy of 79.55%. However, linear SVM and the clustering algorithm showed relatively lower accuracies, suggesting challenges in linearly separating classes or identifying distinct clusters in the dataset.
Visualizations were provided to gain insights into the data distribution, feature importances, and model performance. The count plots of the top important variables from the random forest model highlighted specific game board positions that were more likely to lead to a win for player 1. The scatter plot for clustering showcased the separation of different outcomes based on two selected features, although the clustering algorithm's performance was relatively low, indicating challenges in identifying clear patterns.
Overall, this analysis demonstrated the capabilities and limitations of different machine learning models in predicting the Connect-4 game outcome. Further improvements and explorations can be made by refining existing models, exploring different architectures, or considering alternative clustering algorithms. The findings of this report contribute to a better understanding of the Connect-4 dataset and provide insights into the predictive capabilities of different models for similar classification tasks.

**BIBLIOGRAPHY**

1. Connect-4 Data Set. UCI Machine Learning Repository. (n.d.). Retrieved from
https://archive.ics.uci.edu/ml/datasets/Connect-4
2. Hastie, T., Tibshirani, R., & Friedman, J. (2009). The Elements of Statistical Learning: Data Mining, Inference, and Prediction. Springer, https://link.springer.com/book/10.1007/978-0- 387-84858-7
3. Bishop, C. M. (2006). Pattern Recognition and Machine Learning. Springer, https://link.springer.com/book/9780387310732
4. Mitchell, T. M. (1997). Machine Learning. McGraw-Hill,
https://www.cs.cmu.edu/~tom/mlbook.html
5. Burges, C. J. C. (1998). A Tutorial on Support Vector Machines for Pattern Recognition. Data Mining and Knowledge Discovery, 2(2), 121-167, https://link.springer.com/article/10.1023/A:1009715923555
6. Haykin, S. (1999). Neural Networks: A Comprehensive Foundation. Prentice Hall, https://drive.google.com/file/d/0B2iRDvP8jUuAUnpfaDBnQTBWLUU/edit?resourcekey=0- bq1kH6l5hurYT7TtvylSCQ
7. Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep Learning. MIT Press,
https://www.researchgate.net/publication/320703571_Ian_Goodfellow_Yoshua_Bengio_and_ Aaron_Courville_Deep_learning_The_MIT_Press_2016_800_pp_ISBN_0262035618
8. Aggarwal, C. C. (2018). Neural Networks and Deep Learning: A Textbook. Springer, https://link.springer.com/book/10.1007/978-3-319-94463-0
9. Pan, S. J., & Yang, Q. (2010). A Survey on Transfer Learning. IEEE Transactions on Knowledge and Data Engineering, 22(10), 1345-1359, https://ieeexplore.ieee.org/document/5288526
10. Bengio, Y. (2012). Deep Learning of Representations for Unsupervised and Transfer Learning. Journal of Machine Learning Research, 13, 2493-2537, http://proceedings.mlr.press/v27/bengio12a/bengio12a.pdf
11. Jain, A. K., Murty, M. N., & Flynn, P. J. (1999). Data clustering: A review. ACM Computing Surveys (CSUR), 31(3), 264-323
12. Shlens, J. (2014). A tutorial on principal component analysis. arXiv preprint arXiv:1404.1100
13. Golub, G. H., & Van Loan, C. F. (2012). Matrix computations. JHU Press.’


