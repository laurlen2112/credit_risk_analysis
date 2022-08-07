# Credit Risk Analysis

## Overview:
This analysis trains and compares various machine learning models to predict credit risk.  Various sampling techniques are employed prior to conducting logistic regression on the set and the resuls are compared through the balance accuracy score, the confusions matrix, and classfication report of each algorithm.  The confusion matrix demonstrates the performance of the algorithm by displyaing the number of true positives, false negatives, false positives, and true negatives.  The precision and sensitivity (also called recall) of the algorithm can be determined by adding and dividing the confusion matrix numbers in various combintions.  A classification report performs and displays those computations so they do not have to be performed separately.  Since the balanced accuray score can be misleading in a unbalanced set, it is important to create an imbalanced classifcation report to get a better idea of the true nature of the data.


## Results:
### Deliverable 1: Oversampling, Undersampling, and SMOTE
* Class imbalance occurs where the classes in the dataset are not equally represensted.  Oversampling and undersampling are techniques to adjust an unbalanced dataset.  

* Oversampling:
![oversample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20%20oversample%20all.png)

Oversampling is used to increase minority classes and is used when there are a minority of instances of that class in the training set.  Random oversampling randomly selects data until the minority and majority classes are balanced.

* Undersampling: 
![undersample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20undersample%20all.png)
Undersampling addresses class inmbalance by decreasing the size of the majority class.  Unlike oversampling, undersampling only uses actual data.  However, the drawback to this tecnique is the loss of actual data. 

* SMOTE:
![Smote all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20smote%20all.png)

SMOTE stands for "Synthetic Minority Oversampling Technique" and addresses and imbalanced dataset by oversampling the minority class. SMOTE differs from random oversampling beacuse it generates synthetic observations.  The reliability of SMOTE can be problematic because there is a danager of outliers. 

### Deliverable 2: SMOTEEN
* SMOTEEN is a technique that combines undersampling and oversampling in an effort to deal with an inbalanced dataset.  SMOTEEN adds "EEN" or "Edited Nearest Neighbor" to the SMOTE technique in a two step process.  The first step oversamples the minority class and the second step drops a datapoint if the two nearest neightbors of that datapoint belong to different classes.  

![Smoteen all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%202%20smoteen%20all.png)


### Deliverable 3: Balanced Forrest and 
*

* Balanced Forrest:
![Balanced Forrest](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20bal%20forest%20all.png)

* Easy classifier
![easy classifier](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20class%20bal%20accruacy%20all.png)
