# SOC_pre_Task

## TASK-1:Classification Results and Interpretation<br />
Evaluated the dataset using Logistic Regression, Support Vector Machines (SVM) with various kernels, and K-Nearest Neighbors (KNN). Below are the performance metrics for each model:<br />
 Colons can be used to align columns.<br />

| Model    | Accuracy	          | Precision  | F1 Score|
| ------------- |:-------------:| ---------:|:-------------:
| Logistic Regression (GridSearch tuned)     | 1.0000| 1.0000| 1.0000 |
| SVM (Linear Kernel)    | 1.0000    |   1.0000 | 1.0000 |
| SVM (Sigmoid Kernel)| 0.8500     |    0.8821 | 0.8440 |
| SVM (Polynomial Kernel)| 0.4500 | 0.4750 | 0.3513 |
| K-Nearest Neighbors (K=3) | 0.6500 | 0.8031	| 0.6173 |

![Logistic_Regression](images/Logistic_Regression.png)
![SVM_Linear](images/SVM_Linear.png)
![SVM_poly](images/SVM_poly.png)

<br />The dataset appears to contain strong linear discriminative patterns, which is why Logistic Regression and Linear SVM achieve perfect scores as comapred to poly or rbf kernal. These models thrive when data is well-separated in a linear fashion, and the performance drops with non-linear kernels.
The high precision of KNN suggests it's able to identify positive instances well, but its lower F1-score shows challenges with recall due to local overlaps in feature space.<br />

## TASK-2:Top 5 Feature Identification<br />
Applied three different feature selection techniques to identify the most important contributors to classification:<br />
| Method  |Top 5 Features   | 
| ------------- |:-------------:| 
| Univariate Feature Selection (UFS)   | ['alpha10', 'alpha53', 'delta18', 'delta26', 'gamma30']| 
| Recursive Feature Elimination (RFE)  |['alpha6', 'beta10', 'delta11', 'delta60', 'gamma24'] |   
| Principal Component Analysis (PCA)|['delta55', 'delta62', 'delta23', 'delta10', 'delta52']    |  

![EEG_channels](images/Top_eeg_channels.png)

| Channel ID  |Frequency  |  Reason for Importance|
| ------------- |:-------------:|  ---------:|
| 10  | 3| Strong marker across alpha, beta, and delta bands — consistently selected by all methods (UFS, RFE, PCA), indicating high discriminative power. |
| 6, 11, 18, 23, 24, 26, 30, 52, 53, 55, 60, 62 |1 |   Selected once — potential biomarkers depending on localized brain functions.
