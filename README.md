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

For this study we used `scikit-learn` (`sklearn`) for classical machine learning models and `Pennylane` for the `VQA` classifier. The quantum kernel used for the `QSVC` is imported from `Qiskit`. The `cross_validate` and `train_test_spli` functions were also imported from `sklearn`. 

- LR, CART, KNN, NB, and SVM are implemented with `sklearn`
- QSVC is the SVC algorithm provided by `sklearn` using a quantum kernel available with `Qiskit`. 
- VQC is implemented with `Pennylane`

## Datasets 

We used two datasets: [UCI Credit Card fraud](https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset) and a [Fraud bank dataset](https://www.kaggle.com/datasets/volodymyrgavrysh/fraud-detection-bank-dataset-20k-records-binary). This choice was made to be close to the real-world where datasets have a lot of features. 


## Results 

Below you will find the main results of the paper. 

### UCI Credit Card 

#### Baseline 

| Algorithm | Precision  | Recall | f1-score | Matthews | Balanced | 
| :---: | :---: | :---: | :---: | :---: | :---: |
|     -     |      (%)     |   (%)    |   (%)    | corcorref (%) | Accuracy (%) |
| LR | 0.00 (0.00) | 0.00 (0.00) | 0.00 (0.00) | -0.22 (0.44) | 49.99 (0.01) |
| KNN | **38.74** (2.03) | 15.45 (1.51) | 22.07	(1.76) | 12.43 (0.76) | 54.26 (0.65) |
| CART | 37.79 (1.51) | 40.53 (1.51) | **39.10** (1.34) | **20.99** (1.45) | **60.76** (0.75) |
| NB | 24.71 (0.89) | **88.41** (1.55) | 38.62 (1.15) | 11.94	(1.74) | 55.82 (0.88) |
| SVM | 0.00 (0.00) | 0.00 (0.00) | 0.00 (0.00) | 0.00 (0.00) | 50.00 (0.00) |

#### Quantum 

| Algorithm | Precision  | Recall | f1-score | Matthews | Balanced | 
| :---: | :---: | :---: | :---: | :---: | :---: |
|     -     |      (%)     |   (%)    |   (%)    | corcorref (%) | Accuracy (%) |
| QSVC (SVD) | 20.00 (40.00) | 2.21 (4.82) | 3.92 (8.45) | 5.98 (12.30) | 51.10 (2.41) |
| VQA (SVD) | 77.50 | 26.72 | 39.74 | 19.75 | 58.00 | 
| QSVC (PCA) | 12.00 (29.93) | 1.06 (2.14) | 1.88 (3.84) | 0.51 (8.04) | 49.93 (1.30) |
| VQA (PCA) | **88.10** | 25.87 | 40.00 | 18.95 | 58.55 |  
| QSVC (SKPP) |  0.0 (0.0) | 0.0 (0.0) |  0.0 (0.0) | 0.0 (0.0) | 50.0 (0.0) |
| VQA (SKPP) | 25.58 | 27.5 | 26.51 |  7.3 | 53.75 | 
| QSVC (LDA) | 67.02 (13.31) | 33.44 (10.08) | 43.96 (10.97) | 38.51 (10.97) | 64.6 (5.08) |
| VQA (LDA) | 41.30 | **100.00** | **58.46** | **59.28** | **92.54** |

---

### Fraud bank 

#### Baseline 

| Algorithm | Precision  | Recall | f1-score | Matthews | Balanced | 
| :---: | :---: | :---: | :---: | :---: | :---: |
|     -     |      (%)     |   (%)    |   (%)    | corcorref (%) | Accuracy (%) |
| LR | 71.54 (2.77) |  47.27 (1.96) |  56.88 (1.62) | 46.89 (1.88) | 70.2 (0.88) \\
| KNN | 74.34 (1.77)|  64.56 (2.36) |  69.09 (1.91) | 59.16 (2.65) | 78.22 (1.39) \\
| CART | **80.68** (1.87) | 81.69 (2.06) | **81.17** (1.63) | **74.27** (2.25) | **87.28** (1.21) \\
| NB | 28.43 (1.07) | **96.95** (0.88) | 43.96 (1.3) | 12.58 (1.36) | 54.07 (0.54) \\
| SVM | 0.0 (0.0) | 0.0 (0.0) |  0.0 (0.0) | 0.0 (0.0) | 50.0 (0.0) \\





#### Quantum 


| Algorithm | Precision  | Recall | f1-score | Matthews | Balanced | 
| :---: | :---: | :---: | :---: | :---: | :---: |
|     -     |      (%)     |   (%)    |   (%)    | corcorref (%) | Accuracy (%) |
| QSVC (SVD) |  85.02 (11.42) | 39.24 (8.53) | 52.94 (8.19) |  49.55 (7.54) |  68.45 (3.97) | 
| VQA (SVD) |   62.50 |  72.22 | 60.61 |  26.57 | 74.09 | 
| QSVC (PCA) |   0.0 (0.0) | 0.0 (0.0) |  0.0 (0.0) | 0.0 (0.0) |  50.0 (0.0)| 
| VQA (PCA) |   67.39 | 25.41 | 36.90  | 7.16 | 53.09 | 
| QSVC (SKPP) |   56.28 (11.17) | 46.46 (7.21) |  50.3 (6.8) |  35.53 (8.7) |  66.65 (4.02)| 			
| VQA (SKPP) |  **89.86** | 68.89 | **77.99** | **70.67** | 82.60 | 
| QSVC (LDA) | 82.35 (10.29) | 65.92 (8.79) | 2.93 (8.14) | 66.35 (9.9) | 80.67 (4.94)| 
| VQA (LDA) | 84.00 | **84.44** | 75.68 | 55.81 | **83.92** | 




