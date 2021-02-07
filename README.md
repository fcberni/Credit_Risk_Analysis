# Credit_Risk_Analysis

## Overview of the analysis 

The purpose of this analysis is to utilize Machine Learning to analyze a credit card credit dataset to determine high risk loans versus low risk loans. In order to see what model would work best with this dataset, I attempted four different sampling methods in order to make up for the large numerical difference of low risk to high risk loans. Then I ran a logical regression test on each sampling method. Afterwards, I also ran a RandomForest classifier and a EasyEnsemble classifier totaling to six tests overall. 

## Results

### Oversampling Methods

Each of these methods tried to add towards the minority class, high-risk, in order to make the test more fair.

#### Naive Random Oversampling

![]()

Accuracy score: 66%
True Positives 78	
True Negatives 9283		
False Positives	7821	
False Negatives 23

This test performed average with low precision on high-risk loans and perfect precision on low-risk loans. Recall on both classes were middling with 0.77 low-risk and 0.54 high-risk. Its true positives meaning it predicted high-risk on actual high-risk loans ranked about second out of the tests however the amount of false positives (Predicting high, actually low) is pretty high.


#### Synthetic Minority Oversampling Technique (SMOTE) 

![]()

Accuracy score: 66%
True Positives 64	
True Negatives 11684
False Positives	5420
False Negatives 37

This test performed similarly to Random Oversampling with low precision on high-risk loans and perfect precision on low-risk loans. Recall on both classes were closer with 0.68 low-risk and 0.63 high-risk. This test didn't really excell at any particular result and actually performed worse than Random Oversampling with less true positives and more false negatives (predicting low, actually high).


### Undersampling Methods

This test attempted to take away from the majority class, low-risk, instead.

#### Cluster Centroid Undersampling

![]()

Accuracy score: 54%
True Positives 68	
True Negatives 7105
False Positives	9999
False Negatives 33

The worst performing test overall. Low precision on high-risk loans and perfect precision on low-risk loans is average amongst each test. Recall on both classes are worse closer with 0.42 low-risk and 0.67 high-risk. This test performed worst at determining low risk loans and had so many false positives, it is hard to recommend this sampling method above anything else discussed here.


### Combination Method

This test utilized both oversampling and undersampling.

#### Synthetic Minority Oversampling Technique Edited Nearest Neighbors (SMOTEENN)

![]()


Accuracy score: 65%
True Positives 73	
True Negatives 9789
False Positives	7315
False Negatives 28

This test performed average with low precision on high-risk loans and perfect precision on low-risk loans. Recall on both classes were similar to random oversampling with 0.57 low-risk and 0.72 high-risk. This test did not have any stand out results and performed slightly worse than Random Oversampling.

### Random Forest Classifier 

![]()

Accuracy score: 68%
True Positives 36	
True Negatives 17099
False Positives	5
False Negatives 65

This test performed above average with surprisingly high precision (0.88) on high-risk loans and perfect precision on low-risk loans. It also had perfect recall on low-risk but significantly lower recall on high-risk 0.36. If we wanted to focus on reducing False Positives and increasing predictions on low-risk loans, this test would be a good recommendation. It is the worst at determining high risk loans however.

![top5_features]()

Another benefit of the random forest classifier is seeing how much weight each feature of our dataset contributes to its predictions. This snapshot showcases the top 5 most considered features. 


### Easy Ensemble Classifier

![]()

Accuracy score: 93%
True Positives 93	
True Negatives 16166
False Positives	938
False Negatives 8

This test performed the best overall with 93% accuracy and the typical low precision on high-risk loans and perfect precision on low-risk loans. It had near-perfect recall on low-risk 0.95 and on high-risk 0.92. This model performed the most effective in each category of its confusion matrix. Even though false positives were ones of its weaker points, it still beat out most of the competition.


## Summary

![]()

In the image above I compared the key statistics for each test and color coded them accordingly. The worse performing statistics would highlight closer to red while the ones closer to green would be the best. If I were to recommend the model that would best predict high-risk loans it would be the Easy Ensemble Classifier. 

The EEC performed the best at predicting high-risk loans and second best at predicting low-risk loans. It was especially good at keeping false negatives low which is great for the business. We don't want to give low-risk loans to people who have a bad credit history because otherwise the business would suffer for it. The higher recall or sensitivity does lead to higher false positives however this consequence is easier to overlook than having higher false negatives. This reasoning is why I wouldn't recommend Random Forest unless the business prefers to be more flexible on loaners overall. The sampling techniques also did not perform as well as the extra effort would lead towards Sticking to classifiers or boosters would appear the better alternative for this dataset.