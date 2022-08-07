# Credit Risk Analysis

## Overview:
This analysis trains and compares various machine learning models to predict credit risk.  Various sampling techniques are employed prior to conducting logistic regression on the dataset.  The results are compared through the balance accuracy score, the confusions matrix, and classification report of each algorithm.  

The confusion matrix demonstrates the performance of the algorithm by displaying the number of true positives, false negatives, false positives, and true negatives.  The precision, sensitivity (also called recall), and F1 score metrics can be determined by adding and dividing the confusion matrix numbers in various combinations.  A classification report performs and displays those computations so they do not have to be performed separately.  The precision score calculates the percentage of correct predictions.  The sensitivity or recall score demonstrates the percentage of positive cases flagged.  The F1 score indicates the percentage of prediction that were both positive and correctly predicted.  The balanced accuracy score ranges between 0 and 1.  A balanced accuracy score closer to 1 is a desirable score.  A balanced accuracy score closer to 0 is not a favorable score.  Since the balanced accuracy score can be misleading in a unbalanced set, it is important to create an imbalanced classification report to get a better idea of the true nature of the data.


## Results:
### Deliverable 1: Oversampling, Undersampling, and SMOTE
* Class imbalance occurs where the classes in the dataset are not equally represented.  Oversampling, undersampling, and SMOTE are techniques to adjust an unbalanced dataset.  

* Oversampling:
![oversample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20%20oversample%20all.png)
Oversampling increases minority classes in the training set.  Random oversampling randomly selects data until the minority and majority classes are balanced.  Oversampling is likely not the best technique for this dataset because the classification report shows that the precision in detecting high risk cases is only about 1% and the sensitivity for the same is 66%.  The F1 score is similarly low at about 2% for high risk cases.   

* Undersampling: 
![undersample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20undersample%20all.png)
Undersampling addresses class imbalance by decreasing the size of the majority class.  Unlike oversampling, undersampling only uses actual data.  However, the drawback to this technique is the loss of data.  Similar to the result above, undersampling is likely not the best technique for this dataset since the precision metric and F1 score pertaining to high risk cases is low.  While sensitivity score is slightly higher at about 69%, other techniques may have a better result.

* SMOTE:
![Smote all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20smote%20all.png)
SMOTE stands for "Synthetic Minority Oversampling Technique" and addresses and imbalanced dataset by oversampling the minority class. SMOTE differs from random oversampling because it generates synthetic observations.  The reliability of SMOTE can be problematic because there is a danger of outliers.  As shown above SMOTE, is likely not the best for this dataset since the precision metric and F1 score is low for high risk cases.  Additionally, the sensitivity metric is lowest of the all of the techniques from Deliverable 1.

### Deliverable 2: SMOTEEN
![Smoteen all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%202%20smoteen%20all.png)
SMOTEEN is a technique that combines undersampling and oversampling in an effort to deal with an imbalanced dataset.  SMOTEEN adds "EEN" or "Edited Nearest Neighbor" to the SMOTE technique in a two-step process.  The first step oversamples the minority class and the second step drops a datapoint if the two nearest neighbors of that datapoint belong to different classes.  SMOTEEN provides an improvement to the techniques above.  While the precision metric and F1 score for high risk cases is low, the sensitivity metric is fairly at about 75%.  As discussed below, sensitivity may be a more important metric than precision for this analysis.


### Deliverable 3: Balanced Random Forest Classifier and Easy Ensemble Classifier

* Balanced Random Forest Classifier:   
![Balanced Forrest](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20bal%20forest%20all.png)
Random Forest classifiers select samples from the training dataset and fit each sample to a decision tree.  The Balanced Random Forest randomly undersamples the majority data class in an effort to reach the bootstrap sample.  Here, the precision metric and F1 score is low as it pertains to high risk cases.  However, the sensitivity pertaining t high risk cases is about 70%. Therefore, this technique is demonstrates more sensitivity in detecting high risk cases than the techniques above.

* Easy Ensemble Classifier:
![easy classifier](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20class%20bal%20accruacy%20all.png)
To create balanced samples of the data the Easy Ensemble Classifier uses a subdivision of the majority data and selects all of the minority class.  This technique may be the best technique for this dataset.  It provides the highest precision metric for high risk cases at about 9% and presents with an F1 score of about 16% for the same.  Finally, it shows sensitivity of predicting high risk cases at about 92%.

## Summary:
As alluded to above, the sensitivity or recall score may be the more pertinent score for this data because it is important to correctly identify and flag high risk cases when considering a loan.  There is a tradeoff because that algorithm may incorrectly flag low risk cases as high risk.  However, from a business perspective, it is more desirable to loan money to low risk cases.  As such, the Easy Ensemble Classifier seems to the be the best fit for this data.
