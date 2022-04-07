# Imbalance-Data-Science-Assignment
# Task 1
Assume that we want to compare a new algorithm to a baseline algorithm, for some classification task. 
As we are not sure what hyper-parameter settings to use for the new algorithm, we will investigate 100 different settings for that,
while we use a standard hyper-parameter setting for the baseline algorithm. 
We first randomly split a given dataset into two equal-sized halves; one for model building and one for testing.
We then employ 10-fold cross-validation using the first half of the data, 
measuring the accuracy of each model generated from an algorithm and hyper-parameter setting. 
Assume that the best performing hyper-parameter setting for the new algorithm results in a higher (cross-validation) accuracy than the baseline algorithm.
Should we expect to see the same relative performance, i.e., the new algorithm (with the best-performing hyper-parameter setting) outperforming the baseline (with the standard hyper-parameter setting), 
when the two models (trained on the entire first half) are evaluated on the second half of the data?


Brief summary of my observations:

# Observation 1:

data set-breast-cancer.csv

Baseline crossvalidation accuracy: 0.9438423645320198

best hyper-parameter setting accuracy: 0.9613300492610838

classifier: RandomForestClassifier

best hyper-parameter setting: (n_estimators=50,max_features='sqrt',criterion='entropy',class_weight='balanced',min_samples_split=5)

The number of hyperp parameter settings that outperforms the baseline : 39

baseline accuracy trained on first half evalauated on second half-0.9543859649122807

best-hyper paramater setting accuracy with training on first half and evaluated on second half-0.9438596491228071

The model is most likely biased due to sampling error. Because we have evalauted more than 100 different configurations for the algorithm. The best performing hyper paramter setting accuracy is higher than the baseline accuracy with crossvalidation on the first half of data. Also the number of hyper paramter settings accuracy that outperform the baseline is comparitively low. The overestimation of the performance in first half reflects in the baseline accuracy outperforming the best hyper paramater setting accuracy.

Brief summary of my observations:

# Observation 2:

data set-healthcare-dataset-stroke-data.csv

Baseline crossvalidation accuracy: 0.9176970300315248

best hyper-parameter setting accuracy: 0.9576256844201095

classifier: DecisionTreeClassifier

best hyper-parameter setting: (max_depth=50,max_features=2,min_samples_leaf=10)

The number of hyper parameter settings that outperforms the baseline : 80

baseline accuracy trained on first half evalauated on second half-0.9197556008146639

best-hyper paramater setting accuracy with training on first half and evaluated on second half-0.9572301425661914

The model is also likely biased due to sampling error. Because we have evalauted more than 100 different configurations for the algorithm. The best performing hyper paramter setting accuracy is higher than the baseline accuracy with crossvalidation on the first half of data. But the number of hyper paramter settings accuracy that outperform the baseline is comparitively higher.
The overestimation of the performance in first half does not reflect as the best hyper paramater setting accuracy outperforms baseline.

# Task 2
Performance metrics

Assume that we have evaluated a binary classification model on a test set with 5000 instances; 4000 belonging to the majority class and 1000 to the minority class. Assume that we have measured the accuracy and AUC, and also observed a much higher precision for the majority class than for the minority class. If we would evaluate the model on a class-balanced test set, which has been obtained from the first by keeping all instances from the minority class and sampling (without replacement) 1000 instances from the majority class, should we expect to see about the same accuracy and AUC as previously observed?

# Observation 1:

Data set : dataset_183_adult (income of adults dataset)

type: binary classification

size of test set : 5000 instances- 3804 instances( majority class) 1196 instances(minority class)

size of training set: 15000 instances

classifier: Random forest

Test set AUC: 0.8904884490538036

Test set accuracy : 0.842

Precision of Majority class: 0.88

Precision of minority class: 0.69

size of new test set: 2296 instances- 1196 instances(minority class) 1000 instances(majority class).

new Test set AUC: 0.8879255852842809

new Test set accuracy : 0.7540983606557377

When evaluating with the initial test set with 5000 instances where approximately 4000 majority class and 1000 instances for minority class. The precision of the majority class was higher at 0.89. The accuracy and AUC were observed. When we take a balanced test set from data by keeping all the minority instances and sampling without replacement majority instances, The frequency of the majority class in the test set decreases. So when evaluating the model on the test set, accuracy is reduced also the precision of majority class is reduced. But the AUC almost the same because it is the model's ability to rank the positive instance ahead of the negative instance.
