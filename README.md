# Credit Risk Analysis

## Overview:
This analysis employs and compares various machine learning models to predict credit risk. Before conducting logistic regression on the dataset, various sampling techniques are utilized. The results are evaluated by comparing the balance accuracy score, the confusion matrix, and the classification report of each algorithm.

The confusion matrix illustrates the performance of the algorithm by indicating the number of true positives, false negatives, false positives, and true negatives. Precision, sensitivity (also known as recall), and F1 score metrics can be calculated by adding and dividing the numbers in the confusion matrix in different combinations. A classification report performs these computations and displays the results to avoid the need to perform them individually. The precision score measures the percentage of correct predictions, while the sensitivity or recall score indicates the percentage of positive cases flagged. The F1 score indicates the percentage of predictions that were both positive and correctly predicted. The balanced accuracy score, which ranges from 0 to 1, is desirable when closer to 1 and unfavorable when closer to 0. Since the balanced accuracy score can be misleading in an unbalanced set, generating an imbalanced classification report is essential to obtain a better understanding of the true nature of the data.


## Results:
### Deliverable 1: Oversampling, Undersampling, and SMOTE
* Class imbalance occurs where the classes in the dataset are not equally represented.  Oversampling, undersampling, and SMOTE are techniques to adjust an unbalanced dataset.  

* Oversampling:
![oversample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20%20oversample%20all.png)
To address the imbalance in the training set, oversampling can be employed to increase the instances of minority classes. One approach, random oversampling, involves randomly selecting data until the minority and majority classes are balanced. However, oversampling may not be the most suitable technique for this dataset as the resulting classification report indicates a low precision rate of approximately 1% for identifying high-risk cases, and a sensitivity rate of only 66% for the same. The F1 score for high-risk cases is similarly low at around 2%.  

* Undersampling: 
![undersample all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20undersample%20all.png)
Undersampling is a technique used to handle class imbalance by reducing the size of the majority class. It does not create new data as oversampling does, but instead uses the actual data. However, this method has a disadvantage of data loss. In this case, undersampling may not be the most suitable technique as the precision metric and F1 score for identifying high-risk cases are low. While the sensitivity score is slightly better at around 69%, there may be other techniques that can produce better results.

* SMOTE:
![Smote all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%201%20smote%20all.png)
To address an imbalanced dataset by oversampling the minority class, SMOTE (Synthetic Minority Oversampling Technique) generates synthetic observations instead of simply replicating existing data points, as done in random oversampling. However, SMOTE can be unreliable due to the possibility of generating outliers. As seen in the results above, SMOTE may not be the best technique for this dataset, as the precision and F1 score for high-risk cases are low, and the sensitivity score is the lowest among all the techniques used in Deliverable 1.

### Deliverable 2: SMOTEEN
![Smoteen all](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%202%20smoteen%20all.png)
SMOTEEN is a hybrid sampling technique that combines oversampling and undersampling to tackle imbalanced datasets. It utilizes the SMOTE technique to oversample the minority class and then applies the "Edited Nearest Neighbor" (EEN) algorithm to drop datapoints whose two closest neighbors belong to different classes. SMOTEEN shows promise in improving the previous techniques mentioned. Although the precision and F1 score for high risk cases are still low, the sensitivity metric is relatively high at around 75%. As discussed later on, sensitivity may be a more crucial metric for this analysis than precision.


### Deliverable 3: Balanced Random Forest Classifier and Easy Ensemble Classifier

* Balanced Random Forest Classifier:   
![Balanced Forrest](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20bal%20forest%20all.png)
The Random Forest classifier algorithm selects samples from the training dataset and fits each sample to a decision tree. The Balanced Random Forest is a variant that randomly undersamples the majority class to reach the bootstrap sample. However, similar to the previous techniques, the precision and F1 score metrics are low for high risk cases. Nevertheless, the sensitivity score for high risk cases is about 70%, indicating that this technique is more effective in detecting high risk cases than the previously discussed techniques.

* Easy Ensemble Classifier:
![easy classifier](https://github.com/laurlen2112/credit_risk_analysis/blob/main/resources/del%203%20class%20bal%20accruacy%20all.png)
The Easy Ensemble Classifier subdivides the majority class and selects all of the minority class to create balanced samples. Based on the results, this technique may be the most effective for this dataset. It achieves the highest precision metric for high risk cases at approximately 9% and has an F1 score of around 16% for the same. Moreover, it demonstrates the highest sensitivity in predicting high risk cases at approximately 92%.

## Summary:
As mentioned earlier, the sensitivity or recall score may be more relevant for this dataset because correctly identifying and flagging high-risk cases is crucial in loan assessment. While there is a tradeoff since the algorithm may mistakenly flag low-risk cases as high risk, it is more preferable from a business standpoint to lend money to low-risk cases. Therefore, the Easy Ensemble Classifier appears to be the most suitable technique for this data.
