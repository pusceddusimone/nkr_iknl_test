# NKR IKNL Test
This repository contains the python notebook used to fine tune the following model: https://huggingface.co/dmis-lab/biobert-base-cased-v1.1, the folds.zip files contains the train and validation dataset used in each fold.

## How to run
The script automatically retrieves the folds from the folds directory. Since the code runs on Kaggle, ensure the folds folder is placed in /kaggle/working/folds (or adjust the path as needed).

Both regression and classification are performed using 5-fold cross-validation. Each fold’s dataset is stored in a separate subfolder within the folds directory.
