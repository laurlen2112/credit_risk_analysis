# Credit Risk Analysis

## Overview:
This analysis trains and compares various machine learning models to predict credit risk.  Various sampling techniques are employed prior to conducting logistic regression on the dataset.  The results are compared through the balance accuracy score, the confusions matrix, and classification report of each algorithm.  

The confusion matrix demonstrates the performance of the algorithm by displaying the number of true positives, false negatives, false positives, and true negatives.  The precision and sensitivity (also called recall) of the algorithm can be determined by adding and dividing the confusion matrix numbers in various combinations.  A classification report performs and displays those computations so they do not have to be performed separately.  The precision score calculates the percentage of correct predictions.  The sensitivity or recall score demonstrates the percentage of positive cases flagged.  The F1 score indicates the percentage of prediction that were both positive and correctly predicted.  The balanced accuracy ranges between 0 and 1.  A balanced accuracy score closer to 1 is a good score.  A balanced accuracy score closer to 0 is not a favorable score.  Since the balanced accuracy score can be misleading in a unbalanced set, it is important to create an imbalanced classification report to get a better idea of the true nature of the data.


## Results:
### Deliverable 1: Oversampling, Undersampling, and SMOTE
* Class imbalance occurs where the classes in the dataset are not equally represented.  Oversampling and undersampling are techniques to adjust an unbalanced dataset.  

* Oversampling:
![oversample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20%20oversample%20all.png)

Oversampling is used to increase minority classes and is used when there are a minority of instances of that class in the training set.  Random oversampling randomly selects data until the minority and majority classes are balanced.  

* Undersampling: 
![undersample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20undersample%20all.png)
Undersampling addresses class imbalance by decreasing the size of the majority class.  Unlike oversampling, undersampling only uses actual data.  However, the drawback to this technique is the loss of actual data. 

* SMOTE:
![Smote all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20smote%20all.png)

SMOTE stands for "Synthetic Minority Oversampling Technique" and addresses and imbalanced dataset by oversampling the minority class. SMOTE differs from random oversampling because it generates synthetic observations.  The reliability of SMOTE can be problematic because there is a danger of outliers. 

### Deliverable 2: SMOTEEN
![Smoteen all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%202%20smoteen%20all.png)

SMOTEEN is a technique that combines undersampling and oversampling in an effort to deal with an inbalanced dataset.  SMOTEEN adds "EEN" or "Edited Nearest Neighbor" to the SMOTE technique in a two-step process.  The first step oversamples the minority class and the second step drops a datapoint if the two nearest neightbors of that datapoint belong to different classes.  


### Deliverable 3: Balanced Ranodm Forest Classifier and Easy Ensemble Classifier

* Balanced Ranodm Forest Classifier:   
![Balanced Forrest](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20bal%20forest%20all.png)

Random Forest classifiers select samples from the trainng dataset and fit each sample to a decision tree.  The Balanced Random Forest randomly undersamples the marjority data class in an effort to reach the bootstrap sample.

* Easy Ensemble Classifier
![easy classifier](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20class%20bal%20accruacy%20all.png)

To create balanced samples of the data the Easy Ensemble Classifier uses a subdivision of the majority data and selects all of the minority class.  
