# Time Series Analysis and Classification of Human Activities
This is an interesting task in machine learning for classification of time series. In this notebook, I will classify the activities of humans based on time series obtained by a Wireless Sensor Network. 
This is a comprehensive workflow from data preparation, feature extraction, and preliminary visual analysis, to advanced binary and multiclass classification techniques for identifying human activities based on sensor data.

#### Dataset 
The dataset contains data representing seven types of activities, with each activity's data stored in separate folders. Each folder includes files that have six time series representing different sensors.
The sensors are placed on the body as shown in the figure:
<img width="339" alt="Screen Shot 2024-04-12 at 3 06 42 PM" src="https://github.com/niharikaabhange/Time-Series-Analysis-and-Classification/assets/73836890/fb3e87e8-2cc2-44fe-8954-9be041ce6f59">

Activities include:
1) Bending
2) Sitting
3) Standing
4) Lying
5) Cycling
6) Walking

#### Part 1: Data Preparation and Feature Extraction
 
-> Segregated the dataset for testing and training. Specifically, I kept datasets 1 and 2 in the 'bending1' and 'bending2' folders and datasets 1, 2, and 3 in other folders for testing. The remaining datasets were used for training. 

-> Extracted time-domain features from each of the six time series in all instances. The features I extracted include the minimum, maximum, mean, median, standard deviation, first quartile, and third quartile. 

-> Estimated the standard deviation for each feature and constructed a 90% confidence interval using bootstrap methods to understand the variability and confidence in these estimates.

#### Part 2: Binary and Multiclass Classification
Binary Classification Using Logistic Regression
-> Analyzed bending versus other activities by plotting scatter plots of the time-domain features from specific time series to visually distinguish between these activity types. 
Divided each time series into two equal parts to increase the granularity of the data and then re-plotted the scatter plots to see if this provided better discrimination between activities.

-> Experimented with breaking each time series into multiple segments (up to 20 segments) and used logistic regression to classify bending from other activities, refining the model by selecting features and determining optimal segmentation through cross-validation and feature elimination techniques. 

-> Employed Recursive Feature Elimination with logistic regression to select the most predictive features, validating the model using a stratified cross-validation approach to address potential class imbalance. 

-> Evaluated the model's performance on the training and test sets, focusing on confusion matrices, ROC curves, and AUC metrics to assess classification accuracy and robustness. 
Binary Classification Using L1-Penalized Logistic Regression

-> Applied L1-penalized logistic regression as an alternative method for feature selection and model refinement, which involves cross-validating the number of segments and the regularization strength. 

-> Compared the effectiveness and ease of implementation between models using variable selection through p-values and L1 regularization. 
Multiclass Classification

-> Extended my analysis to classify all activity types using an L1-penalized multinomial regression model, optimizing the number of segments for better performance. 

-> Evaluated different classifiers including Naïve Bayes with Gaussian and Multinomial priors, comparing their effectiveness in a multiclass setting through error metrics and potentially ROC curves for each class. 

