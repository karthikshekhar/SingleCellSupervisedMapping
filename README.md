# SingleCellSupervisedMapping
Goal: Use decision tree ensembles to explore correspondence between two single-cell datasets with cluster labels

Summary: In this tutorial, we use a supervised classification framework to identify the extent to which transcriptionally defined clusters correspond across datasets. The required input is 1) expression matrices corresponding to training data (genes x cells), test data (genes x cells), 2) A set of commonly shared features used for training, and 3) cell type ids for both the training and the testing data. 

The following procedure is implemented in the `xgboost_script.R` file. Please note that to complete the tutorial you will need access to the `XgDataMacaqueBC.rds` file. Please email me at karthikshekhar@gmail.com requesting access. 

1. We train an graph boosted trees classifier (R package xgboost) on a subset of the training dataset using the provided ids. 

2. Next, the classifier is tested on the held-out portion of the training dataset as a validation step, and the results visualized as a confusion matrix (R package ggplot2).

3. Following this, the classifier is applied to the test data after appropriate normalization, such that each test cell is assigned a training id. 

4. The correspondence between the test ids and the classifier-assigned training ids is visualized as a confusion matrix. 
