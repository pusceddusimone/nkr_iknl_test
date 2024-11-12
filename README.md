# NKR IKNL Test
This repository contains the python notebook used to fine tune the following model: [Bio_ClinicalBERT](https://huggingface.co/emilyalsentzer/Bio_ClinicalBERT), the folds.zip files contains the train and validation dataset used in each fold.

## Steps to run
1) Open a new kaggle notebook and import the provided ipynb file
2) Import the following dataset to your kaggle notebook https://www.kaggle.com/datasets/simonepusceddu/nkr-iknl-breast-syntheticdata
3) Add to the /kaggle/working directory the folds inside folds.zip


Classification is performed using 5 fold cross-validation, and the best model is taken from a combination of RMSE, F1 and ROC_AUC, the weights are: (f1 * 0.5) + (roc_auc * 0.3) + (pr_auc * 0.2).
The regressor is trained on the records with vit_stat == 1 and tested on the records predicted as 1 by the previously trained classifier (removing from the training set these records). A second test set with the actual deceased patients is also predicted (given by the actual deceased from the records which were predicted as deceased by the classifier).
