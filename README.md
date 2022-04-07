# Imbalance-Data-Science-Assignment

Assume that we want to compare a new algorithm to a baseline algorithm, for some classification task. 
As we are not sure what hyper-parameter settings to use for the new algorithm, we will investigate 100 different settings for that,
while we use a standard hyper-parameter setting for the baseline algorithm. 
We first randomly split a given dataset into two equal-sized halves; one for model building and one for testing.
We then employ 10-fold cross-validation using the first half of the data, 
measuring the accuracy of each model generated from an algorithm and hyper-parameter setting. 
Assume that the best performing hyper-parameter setting for the new algorithm results in a higher (cross-validation) accuracy than the baseline algorithm.
Should we expect to see the same relative performance, i.e., the new algorithm (with the best-performing hyper-parameter setting) outperforming the baseline (with the standard hyper-parameter setting), 
when the two models (trained on the entire first half) are evaluated on the second half of the data?
