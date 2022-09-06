# An-encoding-perspective-for-quantum-classification-advantage-using-NISQ-algorithms
---
This repository contains the notebooks and data used for the paper "An encoding perspective for quantum classification advantage using NISQ algorithms" published on [arXiv](https://arxiv.org/pdf/2208.13251.pdf) By Mancilla J. and Pere C., 2022. 

---

## Content
- [Notebooks](#notebooks)
- [Libraries](#libraries)
- [Datasets](#datasets)
- [Results](#results)

---

## Notebooks 

9 notebooks were made for this study. The objective is to clearly separate each approach and allowing the reader to have all the information for one specific dataset with one specific encoding approach. One notebook called `Baselines_ML` was done to generate the machine learning models baseline. 

List:
- `Baselines_ML.ipynb`: contains the results of the application of Logistic Regression (LR), Decision Tree (CART), k-Neireast Neighbours (KNN), Gaussian Naïve Bayes (NB), and Support Vector Machine (SVM) on the `UCI_Credit_Card.csv` and `fraud_detection_bank_dataset.csv` datasets. 
- `LDA_ML_QML_UCI_Credit_Card.ipynb`: LDA dimensionality reduction applied on the `UCI_Credit_Card.csv` data
- `PCA_ML_QML_UCI_Credit_Card.ipynb`: PCA dimensionality reduction applied on the `UCI_Credit_Card.csv` data
- `SKPP_ML_QML_UCI_Credit_Card.ipynb`: SKPP dimensionality reduction applied on the `UCI_Credit_Card.csv` data
- `SVD_ML_QML_UCI_Credit_Card.ipynb`: SVD dimensionality reduction applied on the `UCI_Credit_Card.csv` data
- `LDA_ML_QML_fraud_bank.ipynb`: LDA dimensionality reduction applied on the `fraud_detection_bank_dataset.csv` data
- `PCA_ML_QML_fraud_bank.ipynb`: PCA dimensionality reduction applied on the `fraud_detection_bank_dataset.csv` data
- `SKPP_ML_QML_fraud_bank.ipynb`: SKPP dimensionality reduction applied on the `fraud_detection_bank_dataset.csv` data
- `SVD_ML_QML_fraud_bank.ipynb`: SVD dimensionality reduction applied on the `fraud_detection_bank_dataset.csv` data

## Libraries

For this study we used `scikit-learn` (`sklearn`) for classical machine learning models and `Pennylane` for the `VQA` classifier. The `cross_validate` and `train_test_spli` functions were also imported from `sklearn`. 

## Datasets 




## Results 


### UCI Credit Card 

#### Baseline 

| Algorithm | Precision (%) | Recall (%) | f1-score (%) | Matthews | Balanced | 
|           |               |            |              | corcorref (%) | Accuracy (%) |
| :---: | :---: | :---: | :---: | :---: | :---: |
| LR | 0.00 (0.00) | 0.00 (0.00) | 0.00 (0.00) | -0.22 (0.44) | 49.99 (0.01) |
| KNN | **38.74** (2.03) | 15.45 (1.51) | 22.07	(1.76) | 12.43 (0.76) | 54.26 (0.65) |
| CART | 37.79 (1.51) | 40.53 (1.51) | **39.10** (1.34) | **20.99** (1.45) | **60.76** (0.75) |
| NB | 24.71 (0.89) | **88.41** (1.55) | 38.62 (1.15) | 11.94	(1.74) | 55.82 (0.88) |
| SVM | 0.00 (0.00) | 0.00 (0.00) | 0.00 (0.00) | 0.00 (0.00) | 50.00 (0.00) |



### Fraud bank 








